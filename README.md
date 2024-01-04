# gdmbenedict.github.io

Link to website: [https://gdmbenedict.github.io/](https://gdmbenedict.github.io/)

This is a github repo I've set up to make a portfolio using Github Pages, you can check it out by clicking on the link above. It'll also double up as a tutorial on how to re-create what I've done with your own portfolio. I've compiled some useful links at the bottom of this readme (though links will be included in the tutorial at the relevent sections) as well as a credits section for anything I used for this project. If you're looking to modify your github profile to use as a portfolio I would recommend using [this guide](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme) instead.

## Tutorial

### Setting up your Website
The first thing to do is to set up your provided Github Page/Website. You can follow the instructions given by github [here](https://pages.github.com) or you can follow the list of steps below. I'll be giving instructions based on using the Github Desktop client, if you're using something else go to the github provided guide instead.

Create your Page by creating a new **Public** respository named: *"[GithubUsername].github.io"* replacing the brackets and username with your own github username.

![Setting Up Repo](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/af44bee0-da9b-4d3b-9258-d8bc4045c2e5)

Clone your repository by clicking on the set up on desktop button on your browser or by clicking the clone respository button on the github desktop client.

![Cloning Repo](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/afb6dd81-ff42-401d-9dba-27299c9ad6ba)

Don't forget to decide what location to clone it to if you want to put it somewhere that isn't the default location.

Great! Your website is now set up. But you won't be able to see it because you haven't put in any code to handle its behaviour or any HTML to handle the front end. In the next section I'll detail how you can get it looking good easily. You can also make an *"index.html"* file and write a little bit of html to test if the website is working.

### Getting a Template
The next thing you want to do is get a template you want to use for your website. You can get one you like from the internet, though I would personally recommend using the website [HTML5up.net](https://html5up.net/) since they have some good free templates for portfolios. I chose the template "Hyperspace" so this tutorial will be specifically on that template (though this should work for any other template from HTML5up.net). Once you have found a template you're happy with click on the download button on the option from the browsing screen, or on the top right of the template screen.

![Template Screen](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/48c2dadf-2276-4a51-95a3-087a4cb50d55)

The template should be downloaded in the form of a .zip file (probably in your downloads folder). Once it's downloaded all you need to do is extract it and send the information to the git repository you cloned onto your computer like the image below. Note that I extract it to the file directly and not to it's own folder. If you do extract it to it's own folder, just move the files in the folder to your git repo root directory.

![template extraction](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/07b5051f-eaa4-4eaf-85e9-648be94a0fb9)

Once you've finished extracting the template all you need to do is commit and to is push it to Github to get your Github Page looking like the template. It might take a while for the Github Page to update, so don't panic if you don't see the changes for a couple minutes.

### Making Your Site Your Own
Now that you have your template downloaded and you Github Page up, you can modify it to fit you better. Let's take a look at where I started from with my Github page to give you an idea on where to start with yours.

![TemplateBase](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/10d02663-8ab3-465b-a870-409560e88a07)

There are a couple things I could do to modift this page. The easiest was is to just change the text in the *"index.html"* file. However, I want to start with something else. The main thing I want to change is the color since I don't think the base color fits me well. To do this I'll need to modify the *".css"* file for the website. Navigate through your Github Page files by going into *"...\[GithubUsername].github.io\assets\css"*. In the css folder find the *"main.css"* file. It should look like the picture below...

![CSSFolderStructure](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/ea741e64-bb3a-42f6-b559-21076a632d6a)

This css file is what informs a lot of the styling for the Github page, it's generally not a great idea to make a lot of changes to the template since that would provide a lot of extra work to do, but it's pretty easy to change the color. What I would recommend doing is using the *"ctrl+f"* search and search the symbol "#". This will bring up all instances of hex codes for colors. Go through your project and record all the colors that appear in the code. Once you have a full list find a color palette you like and map all the colors you plan to use onto the original colors in the css file. I made a text document to record what I was doing with it and to maintain a design that took advantage of the original color distinction.

![Color List](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/a20d7b2b-2325-4d9a-b924-b989eb8438db)

Once I've finished going through and replacing the colors of the page, it looks more like this.

![ChangedColor](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/f9ada0f7-f606-4b07-9fe9-117c5148a64c)

There's also another change I wanted to implement. I wanted to have a circular profile picture for myself at the top of the page. Unfortunetly this template doesn't include any circular pictures. This is pretty easy to add to the css though. To do this we'll go to where images are specified in the css, this was around line 2500. I went and added a new sort of image to the css, this being a "circular_image". If you would want to add this in your own website you can copy the code I used and put it below the the image specification.

```
/*Circular Image*/

.circular_image {
	border-radius: 50%;
	border: 0;
	display: inline-block;
	position: relative;
}

	.circular_image img {
		border-radius: 50%;
		display: block;
	}

	.circular_image.left, .circular_image.right {
		max-width: 100%;
	}

		.circular_image.left img, .circular_image.right img {
			width: 100%;
		}

	.circular_image.left {
		float: left;
		padding: 0 1.5em 1em 0;
		top: 0.25em;
	}

	.circular_image.right {
		float: right;
		padding: 0 0 1em 1.5em;
		top: 0.25em;
	}

	.circular_image.fit {
		display: block;
		margin: 0 0 2em 0;
		width: 100%;
	}

		.circular_image.fit img {
			width: 100%;
		}

	.circular_image.main {
		display: block;
		margin: 0 0 3em 0;
		width: 100%;
	}

		.circular_image.main img {
			width: 100%;
		}
```

Now that the css file has been modified I can add to the HTML for the website and add in a circular image. The HTML file we need to modify is back in the root folder of your Github page. Navigate back to your *"\[GithubUsername].github.io\"* folder and open the file *"index.html"*. Looking through this file I added a little bit of extra html to the intro section to display the image I wanted. I've highlighted the section of code I highlighted.

![highlightedaddition](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/3e08ae91-72bf-4dd6-bfc9-1f656f504f17)

After adding this to the html I had my introduction section of my website looking like this.

![AddedPictureStyle](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/1a747a00-aec7-4258-97ae-e973a38fd4ea)

Now that the picture has been added and the colors have been changed, I find that the Github page is looking mostly how I want it to look. The last thing to do is to go and change the written portions of the website in the html code for it. It's easy enough to distinguish from the rest of the html. I would recommend checking how you're website's coming along by opening the html file with your browser of choice and refreshing the page. Also worth mentioning is that you can switch out the pictures that the template provides for your own, just make sure that you write the file name down properly in the html, like is shown in the picture above (this includes the file extension).

### Connecting To The Outside
Another thing you may want to do for your website is to connecting it to your social media or to other websites. A nice thing about using a template like this is that most of the structure required to enable this is already built in. For example the contact me section at the bottom of the home page for my website (found below)

![Screenshot 2024-01-04 120514](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/6951175b-89ab-4af6-80f9-9aebd24c4d8a)

As you can see in the picture above I've circled some places that require some form of connection to outside the website. To do this we need to use the HTML **href** attribute. Boiled down, this attribute sends the user to the address if an interaction occurs. We'll start by looking at the social media icons. Look for a tag describing the "icon" class in your index file. Once you find it you should see a block of text like the once below.

![Screenshot 2024-01-04 121429](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/d7d5c4cf-e467-4d3c-ad1d-b33929255b0a)

In the above image I've highlighted the hashtag symbol. This is where you will need to put the addresses of where you want the icons to lead to. To get the address to put with a specific icon, go to the related website, navigate to your profile page, and then copy the adress from the address bar at the top of your browser. Then return to index file and paste the address onto the hashtag symbol. Once you do this you should have a result that looks like the picture below.

![Screenshot 2024-01-04 121930](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/5f55e739-c938-4ed7-b007-d9c1d20437ff)

Once the icons are linked, pressing on them should send the user to the specified address, allowing for quick and easy navigations to your other platforms. If the icons you want aren't listed in the section you can check to see if the font you are using supports different icons. In the case of my website it uses "Font Awesome", a list of Font Awesome's icons can be found [here](https://fontawesome.com/icons) if you want to check if the icon you want is supported.

Next we will make the link to email on the page to the user's mail client on their computer. To do this we need to modify the mail portion of the contact section. Look for the Email header in the index file and find the code that look like the picture below.

![Screenshot 2024-01-04 122411](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/49d4ad38-0238-4bb8-b3af-40e9949dead7)

The modifications we have to do for this are a little different than what we had to do for icons, but still very easy. Insteal of adding a link to the **href** attribute we need to the "mailto:" modifier and the address we want emails sent to. So you would write something similar to the code in the picture below, but replacing the email with your own.

![Screenshot 2024-01-04 122716](https://github.com/gdmbenedict/gdmbenedict.github.io/assets/97464794/9b322a6d-1eea-4a34-b76a-3c6565bcedac)

The last thing to link to systems outside of the website is the contact form. Doing this is a little more compleicated since this requires functions not provided by a client side language like HTML. Rather you would need to use PHP or another server side language to have the form work properly. Unfortunetly, Github pages do not support PHP, so this topic won't be covered in this tutorial; Though, if you want to learn how to do this I would recommend [this](https://mailtrap.io/blog/html-form-send-email/) guide on setting up a contact form.

With all that in mind you should have all the tools you need to build your own website.

## Usefeul Links
[github page setup](https://pages.github.com)<br>
[style template and guides](https://www.geeksforgeeks.org/how-to-build-portfolio-website-and-host-it-on-github-pages/)<br>
[free templates website](https://html5up.net/)<br>
[Font Awesome icons](https://fontawesome.com/icons)<br>
