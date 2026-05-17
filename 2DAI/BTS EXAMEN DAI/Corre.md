### Dossier 1
1. Créer la classe Machine
```java
public class Machine {
    private String id;
    private String nom;
    private Double temperatur;
    

    public Machine(String id, String nom, Double temperatur) {
        th9s.id = id;
        this.nom = nom;
        this.temperatur = temperatur;
    }

    public String getId() { return this.id; }
    public String getNom() { return this.nom; }
    public Double getTemperatur() { return this.temperatur; }

    public void setNom(String id) { this.id = id; }
    public void setNom(String nom) { this.nom = nom; }
    public void setTemperatur(Double temperatur) { this.temperatur = temperatur;
}

@Override
public boolean equals(Object obj) {
    if(obj instanceof Machine) {
        Machine m = (Machine) obj;
        return this.id.equalsIgnoreCase(m.getId());
    }
    return false;
}


@Override
public int compareTo(Object o) {
    if (o instanceof Machine) {
        Machine m = (Machine) o;
        return this.id.compareIgnoreCase(m.getId());
    }
}

2. 
public class Atelier extends Machine {
    private ArrayList<Machine> machines;

    public Atelier(String id, String nom, Double temperatur) {
        super(id, nom, temperatur);
        this.machines = new ArrayList<>();
    }

    public boolean addMachine(Machine m) {
        if (!this.machines.contains(m)) {
            this.machines.add(m);
            return true;
        } else {
            return false;
        }
    }

    public boolean removeMachine(String id) {
       for (Machine m : this.machines) {
            if (m.getId().equals(id)) {
                this.machines.remove(m);
                return true;
            }
            return false;
       }
    }

    public ArrayList<Machine> getMachines() {
        return this.machines;
    }
}
```

### Dossier 2 :
1) Côté serveur : 
- Créer une classe Serveur qui écoute sur un port 
- Lire un objet Machine depuis le client 
- Afficher ses informations
```java
public class Serveur {
    private ServerSocket serverSocket;
    ObjectInputStream ois;
    ObjectOutputStream oos;


    public Serveur(int port) {
        try {
            this.serverSocket = new ServerSocket(port);
            System.out.println("Serveur démarré sur le port " + port);
            ios = 

        } catch (IOException e) {
            e.printStackTrace();
        }
    }


    
}