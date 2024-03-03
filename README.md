import java.util.ArrayList;
import java.util.List;

public class GarbageCollectorExample {

    public static void main(String[] args) {
        List<Object> objects = new ArrayList<>();

        for (int i = 0; i < 1000000; i++) {
            objects.add(new Object());
            if (i % 10000 == 0) {
                System.out.println("Number of objects created: " + objects.size());
            }
        }

        objects.clear();
        objects = null;

        // Trigger garbage collection
        System.gc();

        System.out.println("Garbage collection completed.");
    }
}
