# Primeiros Passos com PYTHON

### Primeiro programa em Python

Vamos executar programas em diferentes modos de programação.

#### Programação de modo interativo

Chamar o interpretador sem passar um arquivo de script como um parâmetro exibe o seguinte prompt -

```python
$ python
Python 2.4.3 (#1, Nov 11 2010, 13:34:43)
[GCC 4.1.2 20080704 (Red Hat 4.1.2-48)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Digite o seguinte texto no prompt do Python e pressione Enter -

```python
>>> print "Hello, Python!"
```

Se você estiver executando uma nova versão do Python, precisará usar a instrução print com parênteses como na **impressão \("Hello, Python!"\);** . No entanto, na versão 2.4.3 do Python, isso produz o seguinte resultado -

```text
Hello, Python!
```

#### Programação de modo de script

Chamar o interpretador com um parâmetro de script inicia a execução do script e continua até que o script seja concluído. Quando o script é concluído, o intérprete não está mais ativo.

Vamos escrever um programa Python simples em um script. Arquivos Python possuem extensão **.py** . Digite o seguinte código-fonte em um arquivo test.py -[ Demonstração ao vivo](http://tpcg.io/lsYEBf)

```text
print "Hello, Python!"
```

Assumimos que você tenha o interpretador Python definido na variável PATH. Agora, tente executar este programa da seguinte maneira -

```bash
$ python test.py
```

Isso produz o seguinte resultado -

```text
Hello, Python!
```

Vamos tentar outra maneira de executar um script Python. Aqui está o arquivo test.py modificado -[ Demonstração ao vivo](http://tpcg.io/2hIf1p)

```python
#!/usr/bin/python

print "Hello, Python!"
```

Assumimos que você tenha o interpretador Python disponível no diretório / usr / bin. Agora, tente executar este programa da seguinte maneira -

```text
$ chmod +x test.py     # This is to make file executable
$./test.py
```

Isso produz o seguinte resultado -

```text
Hello, Python!
```

### Identificadores Python

Um identificador Python é um nome usado para identificar uma variável, função, classe, módulo ou outro objeto. Um identificador começa com uma letra A a Z ou a a z ou um sublinhado \(\_\) seguido por zero ou mais letras, sublinhados e dígitos \(0 a 9\).

O Python não permite caracteres de pontuação como @, $ e% nos identificadores. Python é uma linguagem de programação sensível a maiúsculas e minúsculas. Assim, **Manpower** e **mão de obra** são dois identificadores diferentes em Python.

Aqui estão as convenções de nomenclatura para identificadores Python -

* Nomes de classes começam com uma letra maiúscula. Todos os outros identificadores começam com uma letra minúscula.
* Iniciar um identificador com um único sublinhado à esquerda indica que o identificador é particular.
* Iniciar um identificador com dois sublinhados principais indica um identificador fortemente privado.
* Se o identificador também terminar com dois sublinhados, o identificador é um nome especial definido por idioma.

### Palavras reservadas

A lista a seguir mostra as palavras-chave do Python. Estas são palavras reservadas e você não pode usá-las como constantes ou variáveis ​​ou quaisquer outros nomes de identificadores. Todas as palavras-chave do Python contêm apenas letras minúsculas.



| and | exec | not |
| :--- | :--- | :--- |
| assert | finally | or |
| break | for | pass |
| class | from | print |
| continue | global | raise |
| def | if | return |
| del | import | try |
| elif | in | while |
| else | is | with |
| except | lambda | yield |

### Linhas e Indentação

O Python não fornece chaves para indicar blocos de código para definições de classe e função ou controle de fluxo. Blocos de código são denotados por indentação de linha, que é rigidamente aplicada.

O número de espaços no recuo é variável, mas todas as instruções dentro do bloco devem ser recuadas na mesma quantia. Por exemplo -

```python
if True:
   print "True"
else:
   print "False"
```

No entanto, o seguinte bloco gera um erro -

```python
if True:
    print "Answer"
    print "True"
else:
    print "Answer"
    print "False"
```

Assim, no Python, todas as linhas contínuas recuadas com o mesmo número de espaços formariam um bloco. O exemplo a seguir tem vários blocos de instruções -

**Nota** - Não tente entender a lógica neste momento. Apenas certifique-se de que você entendeu vários blocos, mesmo se eles estiverem sem chaves.

```python
#!/usr/bin/python

import sys

try:
   # open file stream
   file = open(file_name, "w")
except IOError:
   print "There was an error writing to", file_name
   sys.exit()
print "Enter '", file_finish,
print "' When finished"
while file_text != file_finish:
   file_text = raw_input("Enter text: ")
   if file_text == file_finish:
      # close the file
      file.close
      break
   file.write(file_text)
   file.write("\n")
file.close()
file_name = raw_input("Enter filename: ")
if len(file_name) == 0:
   print "Next time please enter something"
   sys.exit()
try:
   file = open(file_name, "r")
except IOError:
   print "There was an error reading file"
   sys.exit()
file_text = file.read()
file.close()
print file_text
```

### Declarações de várias linhas

As declarações no Python geralmente terminam com uma nova linha. O Python, no entanto, permite o uso do caractere de continuação de linha \(\\) para indicar que a linha deve continuar. Por exemplo -

```python
total = item_one + \
        item_two + \
        item_three
```

As declarações contidas nos colchetes \[\], {} ou \(\) não precisam usar o caractere de continuação de linha. Por exemplo -

```python
days = ['Monday', 'Tuesday', 'Wednesday',
        'Thursday', 'Friday']
```

### Cotação em Python

O Python aceita aspas simples \('\), duplo \("\) e triplo \(' '' ou" ""\) para indicar literais de string, desde que o mesmo tipo de aspas inicie e termine a string.

As aspas triplas são usadas para abranger a cadeia em várias linhas. Por exemplo, todos os itens a seguir são legais -

```python
word = 'word'
sentence = "This is a sentence."
paragraph = """This is a paragraph. It is
made up of multiple lines and sentences."""
```

### Comentários em Python

Um sinal de hash \(\#\) que não está dentro de uma string literal começa um comentário. Todos os caracteres após o \# e até o final da linha física fazem parte do comentário e o interpretador Python os ignora.[ Demonstração ao vivo](http://tpcg.io/VgbqMb)

```python
#!/usr/bin/python

# First comment
print "Hello, Python!" # second comment
```

Isso produz o seguinte resultado -

```text
Hello, Python!
```

Você pode digitar um comentário na mesma linha depois de uma declaração ou expressão -

```text
name = "Madisetti" # This is again comment
```

Você pode comentar várias linhas da seguinte maneira -

```text
# This is a comment.
# This is a comment, too.
# This is a comment, too.
# I said that already.
```

A sequência de caracteres com aspas triplas também é ignorada pelo interpretador Python e pode ser usada como um comentário de várias linhas:

```text
'''
This is a multiline
comment.
'''
```

### Usando linhas em branco

Uma linha contendo apenas espaços em branco, possivelmente com um comentário, é conhecida como uma linha em branco e o Python a ignora totalmente.

Em uma sessão de intérprete interativa, você deve inserir uma linha física vazia para finalizar uma instrução de múltiplas linhas.

### Esperando pelo usuário

A linha seguinte do programa exibe o prompt, a declaração dizendo "Pressione a tecla Enter para sair", e aguarda o usuário executar uma ação -

```python
#!/usr/bin/python

input("\n\nPress the enter key to exit.")
```

Aqui, "\ n \ n" é usado para criar duas novas linhas antes de exibir a linha atual. Quando o usuário pressiona a tecla, o programa termina. Este é um bom truque para manter uma janela de console aberta até que o usuário termine com um aplicativo.

### Múltiplas instruções em uma única linha

O ponto-e-vírgula \(;\) permite várias instruções na linha única, uma vez que nenhuma instrução inicia um novo bloco de código. Aqui está um recorte de amostra usando o ponto e vírgula -

```python
import sys; x = 'foo'; sys.stdout.write(x + '\n')
```

### Vários grupos de instruções como suítes

Um grupo de instruções individuais, que formam um único bloco de código, são chamadas **suítes** no Python. Instruções complexas ou complexas, como if, while, def e class requerem uma linha de cabeçalho e um conjunto.

As linhas de cabeçalho iniciam a instrução \(com a palavra-chave\) e terminam com dois-pontos \(:\) e são seguidas por uma ou mais linhas que compõem o conjunto. Por exemplo -

```python
if expression : 
   suite
elif expression : 
   suite 
else : 
   suite
```

### Argumentos da linha de comando

Muitos programas podem ser executados para fornecer algumas informações básicas sobre como eles devem ser executados. Python permite que você faça isso com -h -

```text
$ python -h
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Options and arguments (and corresponding environment variables):
-c cmd : program passed in as string (terminates option list)
-d     : debug output from parser (also PYTHONDEBUG=x)
-E     : ignore environment variables (such as PYTHONPATH)
-h     : print this help message and exit

[ etc. ]
```

Você também pode programar seu script de forma que ele deva aceitar várias opções. [Argumentos de Linha de Comando](https://www.tutorialspoint.com/python/python_command_line_arguments.htm) é um tópico avançado e deve ser estudado um pouco mais tarde, depois de passar pelo restante dos conceitos do Python.

