# Computação Gráfica
Repositório de exemplos de códigos em C++ utilizando OpenGL moderna (3.3+) criado para a Atividade Acadêmica Computação Gráfica do curso Ciência da Computação (modalidade híbrida)

Os exemplos estão distribuidos da seguinte maneira:

- Hello 3D e Hello3D-withShaderClass - Projetos base para a atividade prática proposta no Módulo 1 e Atividade Integradora 1. A diferença entre eles é que no Hello3D-withShaderClass utiliza-se uma classe para fazer a leitura dos shaders a partir de arquivos texto.
- Hello 3D - Mesh - Projeto base para a atividade prática proposta no Módulo 2
- Hello 3D - Textures - Projeto base para a atividade prática proposta no Módulo 3
- Hello 3D - Phong - Projeto base para a atividade prática proposta no Módulo 4

Para configurar os projetos em sua máquina, vá para o arquivo HELP-SETTINGS.md

# Instruções Aula Vivencial 20/05/23


- só deve rodar direto no Windows, para Linux ou Mac precisa instalar HELP-SETTINGS.md
- utilizar x86 porque tudo esta compilado para x32 entao x64 nao funciona
- VS 2019 é o unico compativel
	- Conjunto de Ferramentas de Plataforma, trocar para VS 2019

- Print da versao do OpenGL suportada pela maquina
	- OpenGL version supported
	- Abre prompt the comando extra quando rodar
	- Se nao suportar 4.6.0 sem problema, desde que seja 3.3+ tá bom
		- Ja utilizam shaders a partir dessa versao
	- vertex shader e fragment shader sempre tem "#version 450" na primeira linha
		- Versão suportada sem o ponto

 - iFdef __APPLE__
	- precisa descomentar essa parte do codigo
	- <version_major>.<version_minor> e.g. 3.3

- M2 Resposta ao Desafio
	- Instanciando objetos na cena
	- Transformar a piramide num cubo
	- vertices dela estao no setupGeometry()
		- cada vertice tem: 3 primeiros atributos sao a posicao, os outros 3 são a cor
		- layour 3 color
		- vertex buffer object (VBO e vertex array object (VAO)
	- 12 triangulos, 36 vertices, destruindo a piramide


- Vivencial de Hoje:
	- malha macaquinha de exemplo Suzane
	- Feita de vertices, faces e arestas
	- Blender, 3D Max etc. tem diversos formatos
	- Formato wavefront (.obj)
		- Exemplo de formato OBJ
		- vamos considerar que todas as malhas que usamos são triangularizadas
		- nas faces vamos ter 3 ilhas (3 vertices) para descrever cada face
		- para fazer o parser: getLine no C++ e coloca "#include <sstream>" para usar "istringstream"
		inputFile
		istringstream ssline(sline)
		ssline >> word
		ssline >> s.position.x >> ...
	- Tarefa de hoje:
		- pegar as informacoes do vertice
		- podem ignorar vt que sao coordenadas de textura
		- v/vt/vn -> exemplo 1/1/1
			- vertice, vertice com textura, vertice com normal
		- ele começa sempre contando pelo 1, entao precisa dar um -1 para nao causar segmentacao de memoria
	- Alguns OBJ nao tem normais nem coordenadas de textura, cuidado
		- pode nao ter normais, aí fica um //
		- na nossa aula sempre vai ter os 3 v, vt e vn
	- Tarefa de Hoje
		- carregar OBJs bem simples, como o gif no aviso
			- macaquinha com geometrica de 1 cor só, sem as linhas (vermelho)
		- macaquinha e cubo
		- prof vai colocar OBJs padrao no repositorio (pasta suzane)
			- usar suzaneTri porque está triangularizada
		- Usar o gitignore da professora (ignora arquivos de banco de dados), porque o Visual Studio tem gitignore para .obj
			- Colocar os .obj manualmente ao inves de editar o gitignore, porque pode ter arquivos pesados
		- Coloque informacoes de descricao no README
