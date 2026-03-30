### **Etapa 1: Escolha do Problema**

**Problema escolhido:** Criar uma função em Python que calcule a média de uma lista de notas de alunos e retorne apenas as notas que estão acima dessa média.

---

### **Etapa 2: Primeira Iteração (Vaga) e Resposta Ruim**

**Prompt Vago:** \> "Faz um código de média em Python aí."

**Documentação da Resposta Ruim:** A IA provavelmente retornaria algo extremamente genérico como:

Python  
notas \= \[10, 5, 8\]  
media \= sum(notas) / len(notas)  
print(media)

* **Por que é ruim?** Não possui tratamento de erros (se a lista estiver vazia, o código quebra), não segue boas práticas de documentação, não filtra os alunos acima da média (que era meu objetivo implícito, mas não dito) e não tem estrutura de função reutilizável.

---

### **Etapa 3: Aplicando a Equação do Prompt**

Vou estruturar agora o **Prompt Mestre** utilizando os pilares solicitados:

* **Persona:** Desenvolvedor Python Sênior focado em Clean Code.  
* **Contexto:** Estou desenvolvendo um módulo de análise de dados para um sistema escolar e preciso de uma função robusta para processar o desempenho de turmas.  
* **Restrições:** Use *Type Hints*, inclua *Docstrings* no formato Google, trate exceções para listas vazias ou com dados não numéricos, e não utilize bibliotecas externas (como NumPy).  
* **Formato:** Saída em Markdown estruturado com explicação detalhada.

---

### **Etapa 4: Refinamento Iterativo (Resultado Perfeito)**

**Prompt Mestre Final:**

"Atue como um Desenvolvedor Python Sênior. Preciso de uma função para um sistema escolar que receba uma lista de notas (floats/ints). A função deve calcular a média aritmética e retornar um dicionário contendo a média calculada e uma sublista apenas com as notas que foram estritamente superiores à média. Restrições: Utilize Type Hints, Docstrings completas, trate o erro de divisão por zero caso a lista venha vazia e garanta que o código siga os princípios do Clean Code. Formate o resultado final em Markdown."

**Resultado Gerado (Exemplo de Saída Esperada):**

Python  
from typing import List, Dict, Union

def analisar\_desempenho\_turma(notas: List\[Union\[int, float\]\]) \-\> Dict\[str, Union\[float, List\[float\]\]\]:  
    """  
    Calcula a média de uma lista de notas e filtra os desempenhos acima da média.

    Args:  
        notas (List\[float\]): Uma lista contendo as notas dos alunos.

    Returns:  
        Dict: Um dicionário com a 'media' (float) e 'acima\_da\_media' (list).

    Raises:  
        ValueError: Se a lista estiver vazia ou contiver valores não numéricos.  
    """  
    if not notas:  
        raise ValueError("A lista de notas não pode estar vazia.")

    try:  
        media \= sum(notas) / len(notas)  
    except TypeError:  
        raise ValueError("A lista deve conter apenas números.")

    notas\_acima \= \[nota for nota in notas if nota \> media\]

    return {  
        "media": round(media, 2),  
        "acima\_da\_media": notas\_acima  
    }

\# Exemplo de uso  
try:  
    resultado \= analisar\_desempenho\_turma(\[7.5, 8.0, 5.0, 9.5, 6.0\])  
    print(f"Resultado: {resultado}")  
except ValueError as e:  
    print(f"Erro: {e}")

---

### **Script de Explicação (O que foi feito)**

Este script resume o processo realizado para a Profª. Kadidja Valéria:

1. **Identificação da Falha:** Começamos com uma instrução "vaga" que resultou em um código simplista e perigoso para produção (sem tratamento de erros).  
2. **Engenharia de Prompt:** Aplicamos a **Equação do Prompt**. Ao definir a **Persona** (Sênior), forçamos a IA a adotar padrões de projeto elevados. Ao dar o **Contexto** (sistema escolar), ajudamos a IA a entender a finalidade do dado.  
3. **Estabelecimento de Limites:** As **Restrições** foram cruciais para evitar o uso de bibliotecas pesadas e garantir que o código fosse legível e tipado (Type Hints).  
4. **Entrega Estruturada:** O resultado final não foi apenas um "script", mas uma solução documentada e pronta para ser integrada a um projeto real, entregue no formato Markdown conforme solicitado.  
5. **Refinamento:** O processo mostra que a qualidade da saída da IA é diretamente proporcional à precisão e estrutura da entrada (prompt).

