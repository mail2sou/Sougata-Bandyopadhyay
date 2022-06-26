# Exploratory Testing of Monefy app
## Author: Sougata Bandyopadhyay

### Charter:
    * The Monefy money management app is being targetted for this exploratory testing session. It is an app which helps you tracks your expenses successfully.

### Areas:
    * The areas which were explored in this testing session were the initial onboarding tutorial page, the one time offer page, the home screen of the app, the filter screen, the search screen, the transfers screen, the more options screen (inclusive of categories, accounts, currencies and settings)

### Risks:
    * No requirement document was available to understand the functionality or goal of the application under test and hence the exploratory testing was done from the user prespective
    * I did not take the pro subscription and started to explore the app functionality of a normal subscription

### Mitigations:
    * Having a prior knowledge about the business goal for the application or critical business flows would have helped to prioritize right areas for testing
    * In real time projects, this is where the to and fro communication helps. If we take a "Shift Left" approach in testing it helps to mitigate these risks as you know about the product and which type of customer base it is intended to target along with the goal of the app. This can help us plan our time for each charter based on the final goal of the app.

### Questions:
    * How easy it is to get started with the app for a new cutomer?
    * Do I need to disclose in any sensitive information while using the app?

### Setup:
    * I have just installed the app in my iPhone and plan to get started with the testing

### Charters:
    1. The app is installed and opened for the first time. /High/ (Planned time: 20mins, Time taken: 15mins)
        * The Onboarding tutorial screen with three sliders is visible, nice color and fonts, clearly visibility /Happy/
        * Nice insights on "What" and "How" to reach financial goals using this app /Happy/
        * The app forces me to click on the "GET STARTED" button or the "dots (.)" present on the bottom of screen to scroll throgh the onboarding screen sliders. It should allow me to side scroll and read through the screens. I got confused how to proceed ahead as being a new app I was reluctant to click on the "GET STARTED" button immediately without going through onboarding tutorial. /Idea/
        * In the third slider of onboarding tutorial screen, when I click on "I AM READY" button, the app redirects me to the one time welcome offer screen. /Happy/

    2. Nice "One-time welcome offer" screen, immediately catches the attention and someone who wants to go for the offer can easily navigate to the "CLAIM MY OFFER" button /Medium/ (Planned time: 15mins, Time taken: 15mins)
        * Privacy Screen and Terms of Use links are working as expected and opens in default mobile browser. /Happy/
        * I wantedto read the reviews (with 5 stars it shows 127k reviews), no hyperlink redirected me to the review page. Being a new user I would have loved to read the reviews to understand user experience straight away. /Idea/
        * I click on the "X" button in the top right corner and it navigates me to a new screen /Happy/

    3. Home Page of the app /Critical/ (Planned time: 45mins, Time taken: 50mins)
        * Nice look and feel - different symbols as categories of income or expense /Happy/
        * Clicking on any of those images takes me to the expense screen. Why not income screen? I might want to add income as well /Idea/
        * The app has two big "-" and "+" buttons on the bottom of the screen with two colors. I assume "New income" button is colored as green and "new expense" as red. However, once I click the "new expense" button why isn't the color pallete for following screen kept as red, to suggest it is an expense? Worth giving a thought /Idea/
        * Why is the currency defaulted to "$"? Can't this be based on the app store country currency? Or user gets an option to choose and change the currency? /Question/
        * I added one expense of 5$ and one income of 10$, both got successfully added /Happy/
        * However, the donut chart in the middle of the screen turns red instead of green. I have more income than expense so the donut chart should be displayed in green. /Bug/
        * I updated my income but still the donut chart stays red /Bug/
        * The color of the balance button is displayed as expected (green when income is more than expense and vice versa) /Happy/
        * Now when I add an expense which is more than my current income, the donut chart turns "orange". I do not understand this. What is wrong with this donut chart color? /Bug/
        * Search with words works as expected and the app searches with partial word as well (returns with color) /Happy/
        * I cannot search with the amount. What if I forgot what I had written while creating the expense and want to search with the amount /Bug/
        * When I click on the donut chart, the color changes and it shows me the last expense I had put in. Why? /Question/
        * I can see the history by clicking on the lines on the bottom of the screen /Happy/
        * I can add backdated expense or income and view them /Happy/
        * If I add any expense or income, after successfully adding it, the snackbar below regarding the expense stays for as long as 10 seconds /Bug/

    4. The Filter screen on the left side of the home screen /High/ (Planned time: 15mins, Time taken: 15mins)
        * The filter works as expected and shows me records of different day or week or month or specific intervals /Happy/
        * The calendar used is working as expected and fetching records /Happy/
        * After choosing one of the visa card or cash, only the expenses related to them is displayed /Happy/

    5. The "Transaction Arrow" icon on the top of the screen opens up new transfer screen /High/ (Planned time: 15mins, Time taken: 15mins)
        * New transfer screen should have a "Back arrow button" to cancel the transaction and return to the Home screen /Bug/
        * New transfer screen should have active cursor in input of transaction amount. For example, as soon as I enter this screen the cursor should be by default in the text bo and the keypad should be open /Idea/
        * New transfer screen should give provide with an option to select between the money space to transfer from and to /Happy/

    6. The "more options" on the right most corner of the screen /High/ (Planned time: 45mins, Time taken: 43mins)
        * Once clicked, a panel swiftly opens up to show "Categories", "Accounts", "Currencies", "Settings" /Happy/
        * I can go further into each of them, by tapping either of those 4 types /Happy/
        * To return back to the main panel, I can tap the type again and it redirects me to the main panel /Happy/
        * Clicking on "Settings", multiple options open up /Happy/
            * Clicking on check box "Budget Mode", asks me to put in budget, only numbers allowed, happy to see this basic but mandatory validation /Happy/
            * Why is the "Monthly budget amount", defaulted to 0. I have to delete this amount and then put in my budget. I would have preffered the amount to be defaulted to blank as soon as I click on the text box to edit the Monthly budget /Idea/
            * Once "Monthly Budget amount" is entered, the budget gets displayed, but what does it do? I added expense more than the monthly budget, but didnt get any alert or no response from the app /Bug/
            * The checkbox "Carry over" if checked, shows the carry over amount from the earlier months or years (as per interval selected) /Happy/
            * Not sure what "Future Recurring expense" does here /Question/
            * If I change currency, the currency conversion does not happen. Rather all the expenses are shown in a different currency. So users, who has multi currency income or expense can't manage it together with this app /Bug/
            * Other things available to normal subcribers like selection of Language, First day of week, First day of the month works as expected /Happy/
            * Whichever options are only for the paid pro subrciption can be highlighted as "PRO", so that the customers can understand what are the advantages of being a pro subcriber and can opt in or out as per thrir choice /Idea/
            * Did not test Synchronization and Data Backup - because I am using my personal phone and do not want to synchronize data /Out of scope/
        * The "Currency" link is present in two places in the More Options screen. First inside "Settings" --> "Currency", here I am allowed to choose a currency and change it as per my choice. However, in the second place "More Options" --> "Currencies" if I click on the "Currencies button", I get naviagted to offer page. I am confused about this behaviour and what is the difference between these two "Currencies" /Question/
        * When I click on "Accounts" link, I see I can add up "New Transfer" and "New Account" /Happy/
            * Adding up "New Accounts" is interersting, as it gives me lots of options related to different cards, currencies and exchange rates options as well /Happy/
            * Name of the account can be customised, which is good and accepts all characters in the name /Happy/
            * I can have initial account balance and initial balance date /Happy/
            * Again, initial account balance is defaulted to 0, so I have to delete and put in customised amount /Bug/
            * Exchange rates is for pro subcribers, so did not test this as I didnt opt for that offer /Out of scope/
            * I could successfully create a new account with my chosen currency, initial balance date and initial accoount balance /Happy/
            * When I create a new account with some balance with "Included in the balance" flag on, the balance in "all accounts" shows up from the next day. Not sure of this behaviour is expected /Happy/
        * When I click on "Categories", I see a list of categories as expense and income /Happy/
            * Most common expense types are covered and I think the respective images are also very relevant /Happy/
            * I can create new categories if I am a pro subcriber. For me this is out of scope /Out of Scope/
            * I am able to change category type name and customise it as per my requirements /Happy/
            * I can also see that I can have 3 types of income categories, the very basic ones for normal users but as a start I am ok with it /Happy/
            * Again, I can customise the names or select my own images, just like I can do for an expense /Happy/

### Prioritisation of Charters:
    * The onboarding tutorial screen with three sliders is the first screen of the app, so have to be explored first. As this is an impression maker screen, this was prioritised the most.
    * Second priority was given to the "One-time welcome offer" screen, again for me this was a medium priority scenario because from a customer perspective I will go for the paid subscription only if I like the app (incase I am not a returning customer). Based on the customer experience, I will decide whether to go for the paid pro subscription.
    * Next was was the home screen, the most important charter as per me as most of the functionality of the app happens here. This is of utmost priority.
    * The next priority is the filter screen because when I have lots of expense to add and I will start viewing them then the filter will help me get the correct records.
    * The fifth priority will be my "Transaction Arrow" screen which help me to add transactions and view them later.
    * The next priority will be my "More options" screen and the functionalities present here is quite a lot but important as well as customers can customise the app as per their needs.

### Defects:
    * However, the donut chart in the middle of the screen turns red instead of green. I have more income than expense so the donut chart should be displayed in green.
    * I updated my income but still the donut chart stays red.
    * Now when I add an expense which is more than my current income, the donut chart turns "orange". I do not understand this. What is wrong with this donut chart color?
    * I cannot search with the amount. What if I forgot what I had written while creating the expense and want to search with the amount.
    * If I add any expense or income, after successfully adding it, the snackbar below regarding the expense stays for as long as 10 seconds.
    * New transfer screen should have a "Back arrow button" to cancel the transaction and return to the Home screen.
    * Once "Monthly Budget amount" is entered, the budget gets displayed, but what does it do? I added expense more than the monthly budget, but didnt get any alert or no response from the app.
    * If I change currency, the currency conversion does not happen. Rather all the expenses are shown in a different currency. So users, who has multi currency income or expense can't manage it together with this app.
    * Again, initial account balance is defaulted to 0, so I have to delete and put in customised amount.
