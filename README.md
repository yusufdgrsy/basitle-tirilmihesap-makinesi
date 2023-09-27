# basitle-tirilmihesap-makinesi
Bu Java programı, kullanıcının iki sayı girmesini ve ardından bir işlem seçmesini sağlar (+, -, *, /). Kullanıcı "q" tuşuna basarak programdan çıkabilir. İşlem sonucunu hesaplar ve ekranda gösterir. 
import java.util.Scanner;

public class HesapMakinesi {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double sayi1, sayi2, sonuc;
        char operator;

        while (true) {
            System.out.println("Hesap Makinesi");
            System.out.print("Birinci sayiyi girin: ");
            sayi1 = scanner.nextDouble();

            System.out.print("İşlemi seçin (+, -, *, /) veya 'q' çıkmak için: ");
            operator = scanner.next().charAt(0);

            if (operator == 'q') {
                System.out.println("Hesap makinesi kapatiliyor...");
                break;
            }

            System.out.print("İkinci sayiyi girin: ");
            sayi2 = scanner.nextDouble();

            switch (operator) {
                case '+':
                    sonuc = sayi1 + sayi2;
                    System.out.println("Sonuc: " + sonuc);
                    break;
                case '-':
                    sonuc = sayi1 - sayi2;
                    System.out.println("Sonuc: " + sonuc);
                    break;
                case '*':
                    sonuc = sayi1 * sayi2;
                    System.out.println("Sonuc: " + sonuc);
                    break;
                case '/':
                    if (sayi2 != 0) {
                        sonuc = sayi1 / sayi2;
                        System.out.println("Sonuc: " + sonuc);
                    } else {
                        System.out.println("Hata: Sifira bolme hatasi!");
                    }
                    break;
                default:
                    System.out.println("Hata: Geçersiz işlem!");
            }
        }

        scanner.close();
    }
}
