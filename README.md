# OS-Shutdowner
a basic shutdown class in java


### Class:
```Java
public class ShutdownExample {

    public static void main(String[] args) {
        shutdownComputer();
    }

    public static void shutdownComputer() {
        try {
            String os = System.getProperty("os.name").toLowerCase();

            if (os.contains("win")) {
                // Windows işletim sistemi
                Runtime.getRuntime().exec("shutdown.exe -s -t 0");
            } else if (os.contains("nix") || os.contains("nux") || os.contains("mac")) {
                // Unix veya MacOS işletim sistemi
                Runtime.getRuntime().exec("shutdown -h now");
            } else {
                System.out.println("İşletim sistemi desteklenmiyor.");
            }

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
