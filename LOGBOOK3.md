# Trabalho realizado na Semana #3

## Identificação

- A versão do VBScript (de 1998 até 2014) permitia executar código arbitrário, remotamente, após desligar o safemode do Internet Explorer. 
- A função SafeArrayRedim em certas circunstâncias não verificava apropriadamente o tamanho de Arrays quando ocorria um erro. 
- Isto permite fazer bypass da proteção do IE e manipular a memória com código Shell do adversário. 
- Sistemas afetados:
    - Microsoft Server 2003, 2008, 2008 R2, 2012 e 2012 R2		 

    - Microsoft Windows Vista, 7, 8, 8.1, RT e RT 8.1 

## Catalogação

- Descoberto, em novembro de 2014, pela IBM X-Force Research team. 
- Score CVSS de 9.3 e classificado pela Microsoft como um CVE crítico na maioria dos sistemas afetados. 
- O CWE associado é o CWE 119 e é um exploit do tipo memory buffer (buffer overflow). "write past the end of a buffer". 

## Exploit

- A execução do exploit explora a diferença do alinhamento dos elementos dos arrays (16 bytes) e do alinhamento da heap do Windows (8 bytes). 
- Providenciando uma oportunidade de alterar o tipo de um elemento de um array adjacente, ler o conteúdo e referência original do array.
- Ou seja, é um exploit do tipo Buffer Overflow na Heap que permite a obtenção de controlo. 

## Ataques

- Microsoft rapidamente corrigiu o erro prevenindo o máximo de ataques possíveis, logo não há muitos registos de ataques. 
- Um dano potencial é executar código arbitrário. Caso o usuário seja um administrador, o sistema pode ser comprometido por completo. 
- Num sistema comprometido o atacante poderá: instalar programas; ver, alterar ou deletar dados; criar novas contas com direitos de administrador. 
- Instalar malware adicional no sistema infetado. 
