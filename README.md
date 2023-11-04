# ttgs-superstore

## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Git | [https://git-scm.com/](https://git-scm.com/) | 
| Node | [https://developer.mozilla.org/en-US/docs/Glossary/Node.js](https://developer.mozilla.org/en-US/docs/Glossary/Node.js) | 
| SQL | [https://developer.mozilla.org/en-US/docs/Glossary/SQL](https://developer.mozilla.org/en-US/docs/Glossary/SQL) |

## Description 
In this project I created a command line application using node.js, and SQL, that allows users to input and lookup products, categories, and tags for a store.  

[Walkthrough Video](https://watch.screencastify.com/v/wmWotT2vPnmxnvKdfyqL)


## Code Example 


 
router.get('/', async (req, res) => {
  try {
    const products = await Product.findAll({
      include: [
        {
          model: Category,
        },
        {
          model: Tag,
          through: ProductTag,
        },
      ],
    });
    res.json(products);
  } catch (error) {
    res.status(500).json(error);
  }
});



There was an exceptional amount of typing in this homework, and though it was challenging, it was doable. With everything I've already learned with the Employee database application assignment plus the README generator, the ask was daunting but ultimately, and with some help from my tutor I was able to pull this assignment together.


const router = require('express').Router();
const { Tag, Product, ProductTag } = require('../../models');

// The `/api/tags` endpoint
router.get('/', async (req, res) => {
  try {
    const tags = await Tag.findAll({
      include: [{
        model: Product,
      },
      // {
      //   model: ProductTag,
      //  }, 
      ]
    });
    res.json(tags);
  } catch (error) {
    res.status(500).json(error);
  }
});


router.get('/:id', async (req, res) => {
  try {
    const tag = await Tag.findByPk(req.params.id, {
      include: [{
        model: Product,
      },
      // {
      //   model: ProductTag,
      //  },
    
    ]
    });


## Learning Points 


This project deepened my growing comfort when it comes to navigating node.js, MYSQL as well as command-line verbage and syntax needed to facilitate the functionality of this app. Understanding MYSQL and it's unique conventions was new and different, but not overly difficult or complex relatively speaking. I'm growing more and more interested in this particular module of the class.


## Author Info
Armand Araujo
Age: 28
Location: Santa Barbara, CA

 
* [LinkedIn](https://www.linkedin.com/in/armand-araujo-a82ba2291/) 
* [Github](https://github.com/Armand57araujo) 


## Credits 