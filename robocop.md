O chatbot funciona lendo algumas palavras seleciodas de uma frase e retornando alguma mensagem pre selecionada, por exemplo:

"feliz" - resposta: que bom que vc está feliz!
"Boleto" - irei retornar os boletos em aberto!


Precisamos de uma fonte de perguntas
a partir das perguntas criamos uma fonte de resposta

encontrei duas bibliotecas legais "chatterbot" e "nltk" mas de qualquer forma, ambas vão funcionar com essa fonte de perguntas
exemplo de código simples onde as listas pares e reflections 
```python
def chatbot():
    print("Olá! Eu sou um chatbot. Como posso ajudar?")
    chat = Chat(pares, respostas)
    while True:
        entrada = input(" ")
        if entrada.lower() == 'sair':
            break
        resposta = chat.respond(entrada)
        print("Chatbot: " + resposta)

if __name__ == "__main__":
    chatbot()

```
