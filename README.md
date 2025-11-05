[![YT Short of production](<img width="465" height="570" alt="image" src="https://github.com/user-attachments/assets/139f7d03-14ef-4995-8732-bb6493c0ce8b" />)](https://www.youtube.com/shorts/79FPZo9IJZc)
<iframe width="384" height="683" src="https://www.youtube.com/embed/79FPZo9IJZc" title="60 sekund, UE5 i…gra gotowa?🎮 #unrealengine5 #gamedev #programming #gamedevelopment #programowanie" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

1. Usunąć wszystkie niepotrzebne rzeczy z Levelu
2. Zmienić Character:
  a. Usunąć rozglądanie
  b. Dodaj stałe poruszanie się postaci po planszy razem z Speed Multiplierem
  <img width="967" height="441" alt="image" src="https://github.com/user-attachments/assets/e7e16b3e-55d8-4d8d-a13d-a47470b51396" />
  c. Dodaj poruszanie się lewo/prawo:
  <img width="662" height="432" alt="image" src="https://github.com/user-attachments/assets/61ee0618-3f0c-4584-830a-28683c9b5687" />
  d. Oraz to żeby postać zmieniała pozycję tylko raz:
  <img width="662" height="326" alt="image" src="https://github.com/user-attachments/assets/1a7c1e26-8b0d-44e4-91f2-e26db91728c7" />
  e. Zmień ustawienia kamery postaci:
  <img width="658" height="456" alt="image" src="https://github.com/user-attachments/assets/5260df69-0b28-413b-8cde-432f5cea465a" />
3. Następnie zabrać się za Tworzenie Planszy:
  a. Stworzyć nowego Actor i nazwać go BP_BaseGround
  b. Dodać do niego trzy Plane z takimi ustawieniami:
  <img width="657" height="235" alt="image" src="https://github.com/user-attachments/assets/55ca2630-daca-4c1d-95c0-889dabaa2694" />
    Dodatkowo materiały ustawić jako: BP_Ground oraz BP_Floor
  c. Dodać BoxCollision z takimi ustawieniami:
  <img width="663" height="322" alt="image" src="https://github.com/user-attachments/assets/ae5f3b7e-2a83-4a94-93af-5d2d31fc6dd6" />
  d. Na overlap BoxColision dać overlap:
  <img width="657" height="436" alt="image" src="https://github.com/user-attachments/assets/6c588e62-57bb-450b-81c1-fa1ae8caa7d2" />
4. Stworzyć Actor o nazwie BP_Spawner:
  a. Stwórz zmienną Array które są tablicą klas BP_BaseGround
  b. Stwórz zmienną Counter
  c. Stwórz funkcję SpawnNewGround:
  <img width="657" height="276" alt="image" src="https://github.com/user-attachments/assets/562de49b-2b21-4b3a-a72c-e42b378e5ba2" />
  d. Na BeginPlay wywołać dwa razy tą funkcję:
  <img width="637" height="167" alt="image" src="https://github.com/user-attachments/assets/14b12d23-7586-4475-acb2-713f286424ea" />
5. Stwórz Actor o nazwię BP_Coin:
  a. Dodaj sferę o takich parametrach:
  <img width="657" height="261" alt="image" src="https://github.com/user-attachments/assets/1e97d3fd-543f-4d06-9516-7f234cad956e" />
  b. Dodaj static Mesh Component z takimi paramatrami:
  <img width="662" height="310" alt="image" src="https://github.com/user-attachments/assets/0b82ae97-5133-46f0-9d74-cbcbf134bc78" />
  c. Na komponent Sphere begin overlap dodaj destroy actor
6. Dodaj Actor o nazwię BP_DeathWall
  a. Dodaj StaticMeshComponent:
  <img width="656" height="287" alt="image" src="https://github.com/user-attachments/assets/921b3a9a-3b83-4741-a2e6-09c6cbd87419" />
  b. Dodaj do niego BoxCollision o takich parametrach:
  <img width="662" height="292" alt="image" src="https://github.com/user-attachments/assets/9fd8a657-678f-4553-b10c-07cba9acbd09" />
7. Stwórz BP_Ground1 oraz BP_Ground2 dziedziczące po BP_BaseGround
  a. BP_Ground1:
  <img width="663" height="230" alt="image" src="https://github.com/user-attachments/assets/837d93d1-5363-41b1-b01f-4c06b71e94da" />
  Lokację ChildActorów: 10, 180, 330, 470,580 oraz Y: 320.0
  b. BP_Ground2:
  <img width="651" height="255" alt="image" src="https://github.com/user-attachments/assets/09d16997-08fc-44a8-9b46-0f9a9dd9e004" />
  Lokację ChildActorów: 10, 180, 330, 470, 580 oraz Box 800 i Y: -310
8. Dodać te dwie klasy do tablicy w BP_Spawner
9. Modyfikacja Levelu:
  a. Ustawić PlayerStart na (X=-950.000000,Y=0.000000,Z=100.000000)
  b. Dodać BaseGround na 0
  c. Dodać BaseSpawner na X2000 oraz 0
10. Ustawienia UI
  a. Dodać do GameMode’a nowy HUD: BP_HUD
  b. Dodać nowy folder UI
  c. Dodać dwa Widget Blueprinty dziedziczące po UserWidget: WBP_HUD, WBP_EndGame
  d. WBP_HUD:
  <img width="656" height="292" alt="image" src="https://github.com/user-attachments/assets/ec0bb63d-aca6-47c7-8a20-00380e3ab12d" />
  e. WBP_EndGame:
  <img width="665" height="322" alt="image" src="https://github.com/user-attachments/assets/62787d7e-7085-489b-a6ef-77a3be041de8" />
  f. Zacznijmy w BP_HUD od dodania tych dwóch widgetów:
  <img width="655" height="191" alt="image" src="https://github.com/user-attachments/assets/62853b3c-fb3e-4aa9-89d2-067d7d4b2fc4" />
  g. Stwórzmy te wszystkie funkcję oraz zmienne w BP_HUD:
  <img width="321" height="467" alt="image" src="https://github.com/user-attachments/assets/0561a63b-5a64-474f-b484-35bdad7f8e02" />
  h. SetPoints:
  <img width="658" height="205" alt="image" src="https://github.com/user-attachments/assets/0a7daf86-0c00-4edf-a06a-6c610ea623d1" />
  i. SetIsGameOver:
  <img width="657" height="277" alt="image" src="https://github.com/user-attachments/assets/6a7a0aac-a637-4619-9e5d-3e17b585e076" />
  j. Podpinamy Eventy do BeginPlay:
  <img width="655" height="232" alt="image" src="https://github.com/user-attachments/assets/3c32a746-cb06-4d4a-b848-9a7767d923d7" />
  k. Zmieniamy BP_Coins:
  <img width="632" height="282" alt="image" src="https://github.com/user-attachments/assets/1ac2567f-d9fe-4729-a04d-dc22aa291a57" />
  l. Zmieniamy BP_DeathWall:
  <img width="626" height="301" alt="image" src="https://github.com/user-attachments/assets/e5b91777-48ce-43e8-b582-93aa769a1a8b" />
  m. Dodajemy to do WBP_HUD:
  <img width="600" height="432" alt="image" src="https://github.com/user-attachments/assets/8a63425d-c703-4081-8795-f2e50d5313f8" />
  n. Dodajemy to do WBP_EndGame:
  <img width="645" height="437" alt="image" src="https://github.com/user-attachments/assets/90f6d7af-ac64-4b0a-a6d1-8cf051997d5f" />
  o. Następnie to na button clicked:
  <img width="627" height="173" alt="image" src="https://github.com/user-attachments/assets/9034ea90-4549-4cf7-8d0d-01e11a438902" />
  p. Oraz na koniec pod Event Construct WBP_EndGame podpinamy ten binding:
  <img width="632" height="322" alt="image" src="https://github.com/user-attachments/assets/fdfb2f49-1236-493c-a3b2-caf699582a4e" />
11. Ostatnie finishe - restarowanie gry:
  a. Na koniec do GameMode dodajemy coś takiego:
  <img width="652" height="280" alt="image" src="https://github.com/user-attachments/assets/67c079aa-c258-48ee-a74c-d9d0825040d8" />
  b. Oraz do Charactera:
  <img width="307" height="100" alt="image" src="https://github.com/user-attachments/assets/1df73af9-90f6-490a-8773-76b9215b8a3b" />
