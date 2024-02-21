# Codewars-Style-Ranking-System
Solution for the Kata Codewars Style Ranking System

~~~
public class User {
    int rank = -8;
    int progress = 0;

    int rank () {
        return this.rank;
    }
  
    int progress (){
        return this.progress;
    }
  
    void incProgress (int kyu){
        try {
            if (kyu == 0 || kyu < -8 || kyu > 8) {
                throw new Exception();
            }
        } catch (Exception e) {
            int i = 1/0;
        }
        if (rank < 8) {
            if (kyu == rank) {
                progress += 3;
            } else if (kyu == rank - 1 || (rank == 1 && kyu == rank - 2)) {
                progress += 1;
            } else if (kyu > rank) {
                int d;
                if (rank < 0 && kyu > 0) {
                    d = rank - kyu + 1;
                } else {
                    d = kyu - rank;
                }
                progress += 10 * d * d;
            }
            while (progress >= 100 && rank < 9) {
                rank++;
                if (rank == 8 && progress >= 100){
                  progress = 0;
                  break;
                }
                if (rank == 0) rank++;
                progress -= 100;
            }
        }
    }
}
~~~
