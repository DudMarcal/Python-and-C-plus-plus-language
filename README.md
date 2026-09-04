
## Passo a passo para aprender Python e C++

## Variáveis (Guardar os Dados) 
No Python a tipagem é dinâmica. Python é flexível, não precisa declarar o tipo de variável. 

# Cria uma variável chamada 'umidade' e guarda um número
umidade = 45.2
print(umidade)

# A mesma variável pode ser reutilizada para texto
umidade = "valor inválido"
print(umidade)

Já para C++ que é tipagem estática, precisa-se declarar o tipo da variável antes de usá-la.

float umidade = 45.2;      // Número com casas  decimais
int leitura_bruta = 3100;   // Número inteiro
bool is_chuva = false;     // Verdadeiro ou Falso
String mensagem = "Solo seco"; // Texto

// Você não pode fazer isso:
// umidade = "texto"; // Erro! umidade só aceita números.

## Condicionais (Tomar Decisões)

# Para o Python: 

umidade = ler_sensor()

if umidade < 30:
    print("Irrigar!")      # Ação se a condição for verdadeira
elif umidade < 50:
    print("Solo úmido")    # Ação se a primeira for falsa e essa for verdadeira
else:
    print("Solo molhado")  # Ação se todas as anteriores forem falsas

# Para C++

float umidade = lerSensor();

if (umidade < 30) {
    Serial.println("Irrigar!");
    ligarBomba();            // Chama a função para ligar a bomba
} else if (umidade < 50) {
    Serial.println("Solo umido");
} else {
    Serial.println("Solo molhado");
    desligarBomba();
}

## Loops (Repetir Ações)

# Para Python
Loop 'for' para repetir um número fixo de vezes

for i in range(5):
    print(f"Leitura número {i+1}")

 Loop 'while' para repetir enquanto uma condição for verdadeira

contador = 0
while contador < 10:
    print(f"Contador: {contador}")
    contador += 1

# Para C++

 Loop 'for' para repetir 10 leituras

for (int i = 0; i < 10; i++) {
    float umidade = lerSensor();
    Serial.print("Leitura ");
    Serial.println(i + 1);
    Serial.println(umidade);
    delay(1000);
}

 Loop 'while' para executar enquanto o botão não for pressionado

int contador = 0;
while (digitalRead(BOTAO_PIN) == HIGH) {
    contador++;
    delay(100);
}
Serial.print("Botão pressionado após ");
Serial.print(contador);
Serial.println(" ms");

## Funções (Organizar o Código)

# Para Python
Função que não retorna valor

def saudacao():
    print("Olá, mundo!")

Função que recebe um valor e retorna outro

def ler_sensor(pin, num_leituras=5):
    soma = 0
    for _ in range(num_leituras):
        soma += analogRead(pin)
    return soma / num_leituras

# Para C++ 
Função que não retorna valor (void)

void saudacao() {
    Serial.println("Olá, mundo!");
}

 Função que recebe um valor e retorna outro

float lerSensor(int pin, int numLeituras = 5) {
    float soma = 0;
    for (int i = 0; i < numLeituras; i++) {
        soma += analogRead(pin);
        delay(10);
    }
    return soma / numLeituras;
}

