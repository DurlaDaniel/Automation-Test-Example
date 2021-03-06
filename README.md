Below are some automations test example , that i wrote  while working on projects.

.........................................

describe ('eMag.ro' , () =>{

    it('should have the correct page title' , async () => {    
        await browser.url('https://emag.ro');
        expect(browser).toHaveTitle('eMAG.ro - Libertate în fiecare zi');
    })

    it('wishlist button should be diplayed' , async () => {
        const wishlistButton = await $('#my_wishlist');
        await  expect(wishlistButton).toBeDisplayed;
    })

    it('Emag Genius should have the correct page title' , async () => {   
        const geniusButton = await $('[title = "eMAG Genius"]');
        await geniusButton.click();
        await expect(browser).toHaveTitle('eMAG genius: serviciul tău premium de cumpărături - eMAG.ro');
    })

    it('Search function should work' , async () => {     
        const searchBox = await $('#searchboxTrigger');
        const searchButton = await $('.searchbox-submit-button');
        await searchBox.setValue('tricou');
        await searchButton.click();
        await expect(browser).toHaveTitle('Cauți tricou? Alege din oferta eMAG.ro');
    })

    it('Products on page should work' , async () => {
        const yellowShirtButton = await $('//*[@id="card_grid"]/div[1]');
        await yellowShirtButton.click();     
        await expect(browser).toHaveTitle('Tricou barbati, Atomic, 100% bumbac, Galben, M - eMAG.ro'); 
    })


    it('Should add product to the cart' , async () => {
       const adaugainCosButton = await $('//*[@id="main-container"]/section[1]/div/div[2]/div[2]/div/div/div[2]/form/div[2]/button[1]');
       await adaugainCosButton.click(); 
    })
})

.........................................

describe('cel.ro' , () =>{

    it('should have to correct page title' , async () =>{
        await browser.url('https://www.cel.ro');
        await expect(browser).toHaveTitle('CEL.ro - Cel mai Cel Marketplace');
    })

    it('veziProduseleZilei button should be displayed' , async () =>{
        const veziProdseleZileiButton = $ ('#oferteleSaptamaniiBtn');
        await expect(veziProdseleZileiButton).toBeDisplayed();
    })

    it('veziProduseleZilei button should work' , async () => {
        const veziProdseleZileiButton = $('#oferteleSaptamaniiBtn');
        await veziProdseleZileiButton.click();        
    })
    
    it('inapoiPeSite button should be displayed and work' , async () =>{
        const inapoiPeSiteButton = $('/html/body/header/div[1]/div[2]/a[1]');
        await expect(inapoiPeSiteButton).toBeDisplayed();
        await inapoiPeSiteButton.click();
    })

    it('chat button should be displayed' ,async () => {
        const chatButton = $('/html/body/div/div/button');
        await expect(chatButton).toBeDisplayed;
    })
})

.........................................

describe('webdriver.io', () => {

    it('should load the page' , async () =>{
        await browser.url('https://webdriver.io/')
    })

    it('get started button should work', async () =>{
        const getStartedButton = $('//*[@id="__docusaurus"]/div[4]/header/div/div[2]/a[1]');       
        await getStartedButton.click();
        await expect(browser).toHaveTitle('Getting Started | WebdriverIO');
    })

    it('home button should work', async () =>{
        const homeButton = $('//*[@id="__docusaurus"]/nav/div[1]/div[1]/a[1]');
        await homeButton.click();
    })

    it('search function should work', async () =>{
        const searchButton = $('//*[@id="__docusaurus"]/nav/div[1]/div[2]/div[2]/button');
        const searchTrigger = $('#docsearch-input');
        const broswerObjectButton = $('#docsearch-item-0');
        const homeButton = $('//*[@id="__docusaurus"]/nav/div[1]/div[1]/a[1]');
        await searchButton.click();
        await searchTrigger.setValue('browser');
        await broswerObjectButton.click();
        await expect(browser).toHaveTitle('The Browser Object | WebdriverIO');
        await homeButton.click();
    })

    it('should change theme colour ' , async () =>{
        const changeThemeButton = $('.toggleTrack_32Fl');
        await changeThemeButton.click();
    })
})
