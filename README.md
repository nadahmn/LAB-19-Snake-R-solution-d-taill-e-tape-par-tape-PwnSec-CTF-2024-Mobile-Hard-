# LAB-19-Snake-R-solution-d-taill-e-tape-par-tape-PwnSec-CTF-2024-Mobile-Hard-



 Objectif final
Exploiter une désérialisation YAML vulnérable (CVE-2022-1471) pour instancier une classe cachée BigBoss, qui charge une bibliothèque native et affiche le flag dans logcat.



                          Étape 0 – Préparation environnement

                          

 <img width="593" height="50" alt="image" src="https://github.com/user-attachments/assets/f3379fad-23ad-4a6e-91c0-4e3bf2dca2a0" />

 

1 Extrais jadx-gui

2 Vérifie que Android Studio est bien installé avec Pixel 6

3 Installe apktool (nécessaire pour patcher)



**<img width="785" height="131" alt="image" src="https://github.com/user-attachments/assets/ce0275b2-113c-45df-863f-6808a0577809" />
**



                      ÉTAPE 1 : ANALYSE AVEC JADX-GUI

                      

<img width="532" height="113" alt="image" src="https://github.com/user-attachments/assets/5965704c-35b1-40f8-9b11-e30a0fceb926" />




                Étape 4 : Création du payload YAML (exploitation de la vulnérabilité SnakeYAML)




-> Création du fichier YAML :



<img width="424" height="35" alt="image" src="https://github.com/user-attachments/assets/3e6f6ca3-84e2-4694-9728-bb8ef9209084" />



-> Extrait du fichier MainActivity.smali  :



<img width="348" height="241" alt="image" src="https://github.com/user-attachments/assets/37975d3a-7ca3-417f-8bdf-7e71251f8179" />




<img width="413" height="65" alt="image" src="https://github.com/user-attachments/assets/66572985-ea81-4975-b3a0-01a152fa7eeb" />



-> vérification  de contenu :



<img width="689" height="67" alt="image" src="https://github.com/user-attachments/assets/ea982568-635c-4967-ade4-74ac06efbd2e" />



                                  Étape 6 : Récupération du flag via logcat


                                  
                                  
-> Le flag n’est pas affiché à l’écran, mais imprimé dans les logs système :


# Filtre spécifique avec : 


              adb logcat | grep -i "PWNSEC"


-> Flag attendu :

Le résultat final 

               PWNSEC{W3'r3_N0t_T00l5_0f_The_g0v3rnm3n7_0R_4ny0n3_3ls3}



