# Sistema de Notificações 📢

Projeto desenvolvido em Java para praticar conceitos de Programação Orientada a Objetos (POO), utilizando interfaces e polimorfismo.

## Funcionalidades

- 📧 Envio por E-mail
- 📱 Envio por SMS
- 💬 Envio por WhatsApp
- Escolha do tipo de notificação através de menu

## Conceitos utilizados

- Interface
- Implementação de interfaces
- Polimorfismo
- Classes e objetos
- Scanner para entrada de dados

## Código

```java
import java.util.Scanner;

interface Notificacao {
    void enviar(String mensagem);
}

class NotificacaoEmail implements Notificacao {

    public void enviar(String mensagem) {
        System.out.println("Enviando e-mail: " + mensagem);
    }
}

class NotificacaoSms implements Notificacao {

    public void enviar(String mensagem) {
        System.out.println("Enviando SMS: " + mensagem);
    }
}

class NotificacaoWhatsApp implements Notificacao {

    public void enviar(String mensagem) {
        System.out.println("Enviando WhatsApp: " + mensagem);
    }
}

class ServicoNotificacao {

    public void notificarCliente(Notificacao notificacao, String mensagem) {
        notificacao.enviar(mensagem);
    }
}

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("1 - E-mail");
        System.out.println("2 - SMS");
        System.out.println("3 - WhatsApp");

        System.out.print("Escolha uma opção: ");
        int opcao = sc.nextInt();
        sc.nextLine();

        System.out.print("Digite a mensagem: ");
        String mensagem = sc.nextLine();

        Notificacao notificacao = null;

        if (opcao == 1) {
            notificacao = new NotificacaoEmail();
        } else if (opcao == 2) {
            notificacao = new NotificacaoSms();
        } else if (opcao == 3) {
            notificacao = new NotificacaoWhatsApp();
        } else {
            System.out.println("Opção inválida.");
        }

        if (notificacao != null) {
            ServicoNotificacao servico = new ServicoNotificacao();
            servico.notificarCliente(notificacao, mensagem);
        }

        sc.close();
    }
}
```

## Exemplo de execução

```text
1 - E-mail
2 - SMS
3 - WhatsApp

Escolha uma opção: 2
Digite a mensagem: Promoção disponível

Enviando SMS: Promoção disponível
```

## Autor

Projeto acadêmico desenvolvido para prática de Programação Orientada a Objetos em Java.
