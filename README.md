# FSClient

Az FSClient egy programgyűjtemény, ami az FS2020 repülőgép szimulátorhoz készült azzal a céllal, hogy adatokat olvassunk és küldjünk a szimulátornak. Illetve bizonyos technikák felhasználásával könnyen tudjunk külső eszközöket – kapcsolók, fékszárny, stb – vezérelni. A vezérléshez web böngésző lett felhasználva, mert egyszerűen készíthetünk vizuális elemeket illetve javascriptben programozhatjuk az eszközeinket.

A különböző egységek között MQTT kommuikációs kapcsolat van, itt olvashatsz róla: https://en.wikipedia.org/wiki/MQTT

### MQTTPanel
ez egy InGamePanel, ami a szimulátorba épül be. Lehetőség van SimVar, GameVar, LocalVar változók olvasására és írásárára. Kezelni tudunk eseményfigyelőket – pl ATC – és CoherentGT hívásokat 


### FSGlassCockpit
ez egy C# írt program, ami különbőző csatornákról fogad és küld adatokat és azokat elhelyezi egy MQTT topicban, vagy egy MQTT topicot dolgoz fel. 
-	HTTPServer: a böngészökhőz biztosítja a tartalmat
-	SorosPort: serial/data topicba helyezi a soros port tratalmát
-	vJoy:  vjoy/button topicban
-	Átlátszó böngésző, amit „ráhúzhatunk” egy popup műszerre – G1000
-	https://github.com/jungervin/FSClient/blob/main/doc/images/TransparentWebView.png
