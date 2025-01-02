# ATM 系统的用例圖、類圖、順序圖、協作圖、活動圖設計

### 自動櫃員機(ATM)也稱為ABM（自動銀行機）是一種銀行系統。這個烘焙系統允許客戶或用戶存取金融交易。這些交易可以在公共場所進行，不需要文員、收銀員或銀行出納員。

# 一、用例圖

### 分析：對於銀行的客戶來說，可以透過ATM機啟動幾個用例：存款、提款、查閱結餘、付款、轉帳和改變PIN（密碼）。銀行官員也可以啟動改變PIN這個用例。參與者可能是一個系統，這裡的信用系統就是一個參與者，因為它是在ATM系統之外。

![image](https://github.com/11024153/Software-2/blob/main/%E7%94%A8%E4%BE%8B%E5%9C%96.png)

# 二、類圖

### 分析：類別圖顯示了提款這個用例中各個類別之間的關係，由四個類別完成：讀卡機、帳目、ATM螢幕和取錢機。類別圖中每個類別都是用方框表示的，分成三個部分。第一部分是類別名稱；第二部分是類別包含的屬性，屬性是類別和相關的一些訊息，如帳目類別包含了三個屬性：帳號、PIN(密碼)和餘額；最後一部分包含類別的方法，方法是類別提供的一些功能，例如帳目類別包含了四個方法：開啟、提款、扣錢和驗錢數。
### 類別之間的連線表示了類別之間的通訊關係。例如，帳目類別連接了ATM螢幕，因為兩者之間要直接相互通訊；取錢機和讀卡機並沒有相連，因為兩者之間不進行通訊。有些屬性和方法的左邊有一個小鎖的圖標，表示這個屬性和方法是private的(UML中用’－’表示)，該屬性和方法只在本類中可訪問。沒有小鎖的，表示public(UML中用’+’表示)，即該屬性和方法在所有類別中可存取。若為鑰匙圖標，表示protected(UML中以’＃’表示)，即屬性與方法可在該類別及其子類別中存取。

![image](https://github.com/11024153/Software-2/blob/main/%E9%A1%9E%E5%9C%96.png)

# 三、順序圖

### 分析：假設客戶Joe取20美元，它的序列圖：序列圖顯示了使用案例中的功能流程。我們對取款這個用例分析，它有很多可能的程序，如想取錢而沒錢，想取錢而PIN錯等等，正常的情況是取到了錢，下面的序列圖就對某客戶Joe取20美元，分析它的序列圖。序列圖的頂部一般先放置的是取款這個用例涉及的參與者，然後放置系統完成取款用例所需的對象，每個箭頭表示參與者和對像或對象之間為了完成特定功能而要傳遞的消息。
### 提款這個用例從客戶把卡片插入讀卡機開始，然後讀卡機讀卡號，初始化ATM螢幕，並開啟Joe的帳目物件。螢幕提示輸入PIN，Joe輸入PIN(1234)，然後螢幕驗證PIN與帳目對象，發出相符的訊息。螢幕提供Joe選項，Joe選擇取錢，然後螢幕提示Joe輸入金額，它選擇20美元。然後螢幕從帳目取錢，啟動一系列帳目物件要完成的過程。首先，驗證Joe帳目中至少有20美元；然後，它從中扣掉20美元，再讓取錢機提供20美元的現金。 Joe的帳目也讓取錢機提供收據，最後它讓讀卡機退卡。

![image](https://github.com/11024153/Software-2/blob/main/%E9%A0%86%E5%BA%8F%E5%9C%96.png)

# 四、協作圖

### 分析：協作圖顯示的資訊和序列圖是相同的，只是協作圖用不同的方式顯示而已。序列圖顯示的是物件和參與者隨時間變化的交互，而協作圖則不參照時間而顯示物件與參與者的交互。
### 例如，Joe取20美元的協作圖中我們可以看到，讀卡機和Joe的帳目兩個物件之間的互動：讀卡機指示Joe的帳目打開，Joe的帳目讓讀卡機退卡。直接相互通信的物件之間有一條直線，例如ATM螢幕和讀卡機直接相互通信，則其間畫一條直線。沒有畫直線的物件之間不直接通訊。

![image](https://github.com/11024153/Software-2/blob/main/%E5%8D%94%E4%BD%9C%E5%9C%96.png)

# 五、活動圖

### 分析：客戶插入信用卡之後，可以看到ATM系統運行了三個並發的活動：驗證卡、驗證PIN(密碼)和驗證餘額。這三個驗證都結束之後，ATM系統會根據這三個驗證的結果來執行下一步的活動。如果卡片正常、密碼正確且通過餘額驗證，則ATM系統接下來詢問客戶有哪些要求也就是要執行什麼操作。如果驗證卡、驗證PIN(密碼)和驗證餘額這三個驗證有任何一個通不過的話，ATM系統就把對應的出錯訊息在ATM螢幕上顯示給客戶。

![image](https://github.com/11024153/Software-2/blob/main/%E6%B4%BB%E5%8B%95%E5%9C%96.png)

參考資料:(https://cloud.tencent.com/developer/article/1751593)
