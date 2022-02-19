# Aplicação prática do SVM (Support Vector Machines)

#### **Introdução**

Uma **máquina de vetores de suporte** (_SVM_, do inglês: `support-vector machine`) é um conceito na [ciência da computação](https://pt.wikipedia.org/wiki/Ci%C3%AAncia_da_computa%C3%A7%C3%A3o) para um conjunto de métodos de aprendizado supervisionado que analisam os dados e reconhecem padrões, usado para classificação e análise de [regressão](https://pt.wikipedia.org/wiki/Aprendizagem_de_m%C3%A1quina). O SVM padrão toma como entrada um conjunto de dados e prediz, para cada entrada dada, qual de duas possíveis classes a entrada faz parte, o que faz do SVM um classificador linear binário não probabilístico. Dados um conjunto de exemplos de treinamento, cada um marcado como pertencente a uma de duas categorias, um [algoritmo](https://pt.wikipedia.org/wiki/Algoritmo) de treinamento do SVM constrói um modelo que atribui novos exemplos a uma categoria ou outra. Um modelo SVM é uma representação de exemplos como pontos no espaço, mapeados de maneira que os exemplos de cada categoria sejam divididos por um espaço claro que seja tão amplo quanto possível. Os novos exemplos são então mapeados no mesmo espaço e preditos como pertencentes a uma categoria baseados em qual o lado do espaço eles são colocados.

Em outras palavras, o que uma SVM faz é encontrar uma linha de separação, mais comumente chamada de [hiperplano](https://pt.wikipedia.org/wiki/Hiperplano) entre dados de duas classes. Essa linha busca maximizar a distância entre os pontos mais próximos em relação a cada uma das classes, ver imagem:

![](https://upload.wikimedia.org/wikipedia/commons/3/31/%D7%9E%D7%9B%D7%95%D7%A0%D7%AA_%D7%95%D7%95%D7%A7%D7%98%D7%A8%D7%99%D7%9D_%D7%AA%D7%95%D7%9E%D7%9B%D7%99%D7%9D_%D7%93%D7%95%D7%92%D7%9E%D7%90.jpg)

Essa distância entre o _hiperplano_ e o primeiro ponto de cada classe costuma ser chamada de margem. A SVM coloca em primeiro lugar a classificação das classes, definindo assim cada ponto pertencente a cada uma das classes, e em seguida maximiza a margem. Ou seja, ela primeiro classifica as classes corretamente e depois em função dessa restrição define a distância entre as margens.

**Algumas características:**

- Em caso de [outlier](https://pt.wikipedia.org/wiki/Outlier) a SVM busca a melhor forma possível de classificação e, se necessário, desconsidera o outlier;
- Funciona muito bem em domínios complicados, em que existe uma clara margem de separação;
- Não funciona bem em conjuntos de dados muito grandes, pois exige [inversão de matriz](https://pt.wikipedia.org/wiki/Matriz_inversa) - aumentando a [complexidade computacional](https://pt.wikipedia.org/wiki/Complexidade_computacional_de_opera%C3%A7%C3%B5es_matem%C3%A1ticas) com até o cubo do volume de dados;
- Não funciona bem em conjunto de dados com grande quantidade de ruídos;
Se as classes estiverem muito sobrepostas deve-se utilizar apenas evidências independentes (devido ao fato de não ser muito bom com dados com muitos ruídos);

**Fonte:** [Wikipedia](https://pt.wikipedia.org/wiki/M%C3%A1quina_de_vetores_de_suporte)


#### **Praticando...**

Para atividade prática da utilização do `SVM`, utilizarei o conjunto de dados do [Kaggle](https://www.kaggle.com/) que pode acessar através desse [link](https://www.kaggle.com/prathamtripathi/drug-classification).

**Contexto**

O nosso desafio é _prever_ o resultado dos medicamentos que podem ser prescritos para um determindado paciente, dadas algumas variáveis, como:
- `Age`: idade do paciente;
- `Sex`: sexo;
- `BP`: níveis de Pressão Arterial(PA);
- `Cholesterol`: níveis de colesterol;
- `Na_to_K`: relação de sódio e potássio no sangue do paciente e,
- `Drug`: tipo de medicamento (varáivel alvo);

