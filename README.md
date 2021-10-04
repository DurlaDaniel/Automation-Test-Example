Below is a automation test example , that i wrote  while working on projects.

.........................................

describe ('eMag.ro' , () =>{

    it('should have the correct page title' , async () => {
        await browser.url('https://emag.ro');
        expect(browser).toHaveTitle('eMAG.ro - Libertate în fiecare zi');
    });

    it('wishlist button should be diplayed' , async () => {
        const wishlistButton = await $('#my_wishlist');
        await  expect(wishlistButton).toBeDisplayed;
    });


    it('Emag Genius should have the correct page title' , async () => {
       
        const geniusButton = await $('[title = "eMAG Genius"]');
        await geniusButton.click();
        await expect(browser).toHaveTitle('eMAG genius: serviciul tău premium de cumpărături - eMAG.ro');


    });

    it('Search function should work' , async () => {
       
        const searchBox = await $('#searchboxTrigger');
        const searchButton = await $('.searchbox-submit-button');

        await searchBox.setValue('tricou');
        await searchButton.click();
        await expect(browser).toHaveTitle('Cauți tricou? Alege din oferta eMAG.ro');

    });


    it('Products on page should work' , async () => {

        const yellowShirtButton = await $('//*[@id="card_grid"]/div[1]');
        await yellowShirtButton.click();     
        await expect(browser).toHaveTitle('Tricou barbati, Atomic, 100% bumbac, Galben, M - eMAG.ro'); 
    });


    it('Should add product to the cart' , async () => {

       const adaugainCosButton = await $('//*[@id="main-container"]/section[1]/div/div[2]/div[2]/div/div/div[2]/form/div[2]/button[1]');
       await adaugainCosButton.click(); 
    });

})
