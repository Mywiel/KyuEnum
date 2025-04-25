# KyuEnum
Learning Java here and trying some of the assignments
import java.util.Scanner;

public class Aufgabe2Kyu {
    enum KYU {
        BRAUN(1, "Braun"),
        BLAU(2, "Blau"),
        GRÜN(3, "Grün"),
        ORANGEGRÜN(4, "Orange-Grün"),
        ORANGE(5, "Orange"),
        GELBORANGE(6, "Gelb-Orange"),
        GELB(7, "Gelb"),
        WEISSGELB(8, "Weiss-Gelb"),
        WEISS(9, "Weiss");

        int kyuGrad;
        String farbe;

        KYU(int kyuGrad, String farbe) {
            this.kyuGrad = kyuGrad;
            this.farbe = farbe;
        }
    }

    public static void main(String[] args) {

        int grad;
        String farbe;
        Scanner scanner = new Scanner(System.in);

        System.out.println("Bitte gib deinen Kyu-Grad ein: ");
        grad = scanner.nextInt();
        scanner.nextLine();

        switch (grad) {
            case 1:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.BRAUN.farbe);
                break;
            case 2:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.BLAU.farbe);
                break;
            case 3:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.GRÜN.farbe);
                break;
            case 4:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.ORANGEGRÜN.farbe);
                break;
            case 5:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.ORANGE.farbe);
                break;
            case 6:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.GELBORANGE.farbe);
                break;
            case 7:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.GELB.farbe);
                break;
            case 8:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.WEISSGELB.farbe);
                break;
            case 9:
                System.out.println("Deine Gürtelfarbe ist: " + KYU.WEISS.farbe);
                break;
        }
        System.out.println("\nDie Stufen sehen folgendermaßen aus:");
        KYU[] farben = KYU.values(); //farben[i] = 0-8 (Grad -1)

        for (int i = 0; i < farben.length; i++) {
            System.out.println("Stufe " + (i + 1) + ": " + farben[i]);
        }

        System.out.println("\nWelche Gürtelfarbe trägst du?\n");
        for (KYU element : farben) {
            System.out.println(element.farbe);
        }
        farbe = scanner.nextLine().toUpperCase();

        KYU kyu = KYU.valueOf(farbe.toUpperCase());
        System.out.println("Deine Wahl: " + kyu.farbe + "\nDas bedeutet, du hast den Kyu-Grad: " + kyu.kyuGrad);
        int next = kyu.kyuGrad + 1;
        //next = (Integer)kyu.kyuGrad+1;
        if (next < farben.length) {
            System.out.println("Deine nächste Stufe (" + next + ") ist die Farbe: " + farben[next + 1].farbe);
        } else {
            System.out.println("Du hast die höchste Stufe erreicht!");
        }
    }
}
