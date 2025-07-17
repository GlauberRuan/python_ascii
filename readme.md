Relatório do Projeto: Conversor de Imagem para Arte ASCII com Ordenação
Disciplina: Estrutura de Dados – 2025.1
Professora: Viviane Aureliano
Alunos: Glauber Ruan Felix da Silva e Thiago Henrique dos Santos Gomes

1. Descrição do Problema Resolvido:

O projeto tem como objetivo criar uma aplicação capaz de converter imagens comuns (JPG, PNG, etc.) em arte ASCII, ou seja, uma representação visual da imagem utilizando apenas caracteres de texto. Além disso, permite ordenar essa arte com base na densidade de caracteres em cada linha. O sistema gerencia múltiplas tarefas simultâneas e oferece uma interface web para upload e visualização dos resultados.

2. Justificativa da Escolha do Tema:

Escolhemos este tema por ser criativo, desafiador e por permitir aplicar diversas estruturas de dados estudadas na disciplina. Trabalhar com manipulação de imagens, conversão para texto e ordenação visual permitiu explorar o potencial prático de algoritmos e estruturas de dados em um projeto tangível e interessante.

3. Estruturas de Dados Utilizadas e Justificativas:

a) Heap Mínimo:

Utilizada para gerenciar as tarefas de processamento. Cada tarefa é inserida na fila com prioridade baseada no tamanho da imagem (quanto menor, maior a prioridade). Essa estrutura permite que tarefas menores sejam processadas mais rapidamente, otimizando o tempo total de resposta.

b) Lista Encadeada (Histórico):

Empregada para armazenar o histórico das últimas 10 tarefas processadas. Foi escolhida por permitir inserção eficiente no final e remoção fácil do início quando o limite é atingido.

c) Dicionário (Banco de Dados Temporário):

Usado para armazenar informações das tarefas, como status, caminho da imagem, resultado em ASCII, etc. Foi escolhido pela eficiência no acesso direto via identificador único (UUID).

4. Desafios Enfrentados e Soluções Encontradas:

Desafio 1: Gerenciar várias tarefas simultaneamente.  
Solução: Utilização de uma thread em segundo plano para processar tarefas sem travar a aplicação web.

Desafio 2: Controlar o tamanho do histórico. 
Solução: Implementação de uma lista encadeada com limite de 10 elementos.

Desafio 3: Ordenar as linhas da arte ASCII por densidade. 
Solução: Uso do algoritmo HeapSort adaptado para comparar a quantidade de caracteres "não vazios" em cada linha da arte.

Desafio 4: Limpar arquivos temporários após o uso. 
Solução: Deleção dos arquivos após conclusão da tarefa.

5. Instruções para Executar o Projeto:

5.1.	Certifique-se de ter o Python instalado.
5.2.	No terminal, crie e ative um ambiente virtual (opcional):
5.3.	python -m venv venv
5.4.	venv\Scripts\activate  # Windows
source venv/bin/activate  # Linux/macOS
5.5.	Instale as dependências:
pip install flask pillow
5.6.	Execute o arquivo principal:
python app.py
5.7.	Acesse no navegador:
http://localhost:5000
5.8.	Envie imagens, aguarde o processamento e visualize a arte ASCII.

