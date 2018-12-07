<template lang="pug">
#IntroducingEagle.eg-theme-agrume
  .eg-slideshow
    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 Hello World
        //- img(src='./assets/logo.svg')
        h4 We Queen And Donnie
        eg-triggered-message(:trigger='slideTimer >= 2',
                            :duration='6', position='top right',
                            enter='bounceInRight', leave='bounceOutRight')

    slide(:steps=4, enter='bounceInRight' leave='bounceOutDown')
      h3
        | Intro Laravel
      .center
        eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
          p(v-if="step >= 2")
            <b>Intention</b>
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if="step >= 3")
            <b>PHP</b>
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if="step >= 4")
            <b>OOP</b> ( Object Oriented Programming)

    slide(:steps=6, enter='bounceInDown')
      h3 What's in it for you

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=2')
          img(src='./assets/icons/basic_paperplane.svg')
          h4 Easy Of Use
          p Detailed Documentation

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=3')
          img(src='./assets/icons/basic_share.svg')
          h4 Open Source
          p Free To Play

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if="step >= 4")
         img(src='./assets/icons/basic_mixer2.svg')
         h4 MVC Architecture
         p Cool Arch

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if="step >= 5")
          img(src='./assets/icons/basic_display.svg')
          h4 Security
          p In Your Hand


    slide(:steps=5, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Windows User

      eg-transition(enter='flipInX')
        p Laragon is a modern, maintained and rich-featured local development environment.

    slide(:steps=4, enter='bounceInRight' leave='bounceOutDown')
      h3
        | Linux User

    slide(:steps=5, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Composer

      eg-transition(enter='flipInX')
        p Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
          php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" <eg-code-comment :active='step === 2' enter='flipInY'> Get installer Composer</eg-code-comment>
          php composer-setup.php <eg-code-comment :active='step === 3' enter='flipInY'> Setup Composer</eg-code-comment>
          mv composer.phar /usr/local/bin/composer <eg-code-comment :active='step === 4' enter='flipInY'> Move File composer.phar</eg-code-comment>
          php -r "unlink('composer-setup.php');" <eg-code-comment :active='step === 5' enter='flipInY'> Remove Composer-setup.php ( Optional )</eg-code-comment>

    slide(:steps=5, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Install PHP

      eg-transition(enter='flipInX')
        p PHP (recursive acronym for PHP: Hypertext Preprocessor) is a widely-used open source general-purpose scripting language that is especially suited for web development

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
          #sudo apt install software-properties-common (18.04)
          #sudo apt install python-software-properties (18.04 below)
          #add-apt-repository ppa:ondrej/php (main php repo)
          #sudo apt update && apt upgrade
          #sudo apt-get install php7.2-fpm
          #sudo apt-get install php-pear php7.2-curl php7.2-dev php7.2-mbstring php7.2-zip php7.2-mysql php7.2-xml

    slide(:steps=4, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Install Laravel ( Via Laravel Installer & Via Composer Create-Project )

      eg-transition(enter='flipInX')
        p Laravel utilizes Composer to manage its dependencies

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
          composer global require laravel/installer <eg-code-comment :active='step === 2' enter='flipInY'> Add Laravel Installer Globaly</eg-code-comment>
          laravel new blog <eg-code-comment :active='step === 3' enter='flipInY'> Create project laravel</eg-code-comment>
          
          composer create-project --prefer-dist laravel/laravel blog <eg-code-comment :active='step === 4' enter='flipInY'> Alternatively Install Laravel</eg-code-comment>
          
    slide(:steps=15, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Directory Structure

      eg-transition(enter='flipInX')
        p The default Laravel application structure is intended to provide a great starting point for both large and small applications. Of course, you are free to organize your application however you like. Laravel imposes almost no restrictions on where any given class is located - as long as Composer can autoload the class.

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
          app <eg-code-comment :active='step === 2' enter='flipInY'> Core code of your application</eg-code-comment>
            - Console <eg-code-comment :active='step === 3' enter='flipInY'> custom Artisan commands for your application </eg-code-comment>
            - Expection <eg-code-comment :active='step === 4' enter='flipInY'> your application's exception handler </eg-code-comment>
            - Http <eg-code-comment :active='step === 5' enter='flipInY'> our controllers, middleware, and form requests </eg-code-comment>
            - Providers <eg-code-comment :active='step === 6' enter='flipInY'> all of the service providers for your application </eg-code-comment>
            - NameProject <eg-code-comment :active='step === 7' enter='flipInY'> Name Project Initial </eg-code-comment>
              - Model <eg-code-comment :active='step === 8' enter='flipInY'> Model </eg-code-comment>
              - Service <eg-code-comment :active='step === 9' enter='flipInY'> Service For Logic Application </eg-code-comment>
          bootstrap <eg-code-comment :active='step === 10' enter='flipInY'> Bootstrap Cache Application </eg-code-comment>
          config <eg-code-comment :active='step === 11' enter='flipInY'> all of your application's configuration files </eg-code-comment>
          database <eg-code-comment :active='step === 12' enter='flipInY'> your database migrations, model factories, and seeds </eg-code-comment>
          public <eg-code-comment :active='step === 13' enter='flipInY'> Directori constains index.php </eg-code-comment>
          resources <eg-code-comment :active='step === 14' enter='flipInY'> un-compiled assets such as LESS, SASS, or JavaScript </eg-code-comment>
          routes <eg-code-comment :active='step === 15' enter='flipInY'> directory contains all of the route definitions for your application </eg-code-comment>
          storage <eg-code-comment :active='step === 16' enter='flipInY'> directory contains your compiled Blade templates </eg-code-comment>
          tests <eg-code-comment :active='step === 17' enter='flipInY'> directory contains your automated tests </eg-code-comment>
          vendor <eg-code-comment :active='step === 18' enter='flipInY'> directory contains your Composer dependencies. </eg-code-comment>
          

    slide(:steps=8, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Let's Start Coding

      eg-transition(enter='flipInX')
        p Config Environment

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').

          # cp .env.example .env <eg-code-comment :active='step === 2' enter='flipInY'> Copy .env.example to .env</eg-code-comment>
          # php artisan key:generate <eg-code-comment :active='step === 3' enter='flipInY'> Generate APP_KEY</eg-code-comment>
          
          DB_CONNECTION=mysql <eg-code-comment :active='step === 3' enter='flipInY'> driver</eg-code-comment>
          DB_HOST=127.0.0.1 <eg-code-comment :active='step === 4' enter='flipInY'> Host </eg-code-comment>
          DB_PORT=3306 <eg-code-comment :active='step === 5' enter='flipInY'> Port</eg-code-comment>
          DB_DATABASE=homestead <eg-code-comment :active='step === 6' enter='flipInY'> Name Database</eg-code-comment>
          DB_USERNAME=homestead <eg-code-comment :active='step === 7' enter='flipInY'> Name User Mysql</eg-code-comment>
          DB_PASSWORD=secret <eg-code-comment :active='step === 8' enter='flipInY'> Password </eg-code-comment>


    slide(:steps=4, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Let's Start Coding

      eg-transition(enter='flipInX')
        p Config Modular Application

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
          
          #Create Folder Project In App

          app
            - Train <eg-code-comment :active='step === 2' enter='flipInY'> Initial Project</eg-code-comment>
              - Model <eg-code-comment :active='step === 3' enter='flipInY'> Create Model Folder</eg-code-comment>
              - Service <eg-code-comment :active='step === 4' enter='flipInY'> Create Service Folder</eg-code-comment>
          
    slide(:steps=4, leave='fadeOut')
      eg-transition(enter='flipInX')
        h3 Let's Start Coding

      eg-transition(enter='flipInX')
        p Setup JWT

      eg-transition(enter='flipInX')
        eg-code-block(lang='html').
    
          #composer require tymon/jwt-auth:dev-develop --prefer-Source <eg-code-comment :active='step === 2' enter='flipInY'> Install package jwt </eg-code-comment>

          Tymon\JWTAuth\Providers\LaravelServiceProvider::class, 

          'JWTAuth' => Tymon\JWTAuth\Facades\JWTAuth::class, 
          'JWTFactory' => Tymon\JWTAuth\Facades\JWTFactory::class,

          php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"

          #php artisan jwt:secret
    //- slide(:steps='5' enter='fadeIn' leave='fadeOut')
    //-   h3 Presenter Mode
    //-   p.center What if I'm too lazy and cannot remember my notes when doing a presentation?
    //-   .center
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 2")
    //-         | By default pressing P toggles Presenter Mode
    //-     eg-transition(enter='bounceInRight' leave='bounceOutRight')
    //-       p(v-if="step >= 3")
    //-         | You have a cloned child view which shares parent's control
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 4")
    //-         | Then on parent window you can have all the fun!
    //-     eg-transition(enter='fadeIn' leave='fadeOut')
    //-       eg-modal(v-if="step >= 5")
    //-         h3 PUSH THE P BUTTON NOW!!:
    //-         .center
    //-           img(:src="preloadedImages['pushButton']",
    //-               :style="{height: '10em'}")

    //- slide(:steps='5' enter='fadeIn' leave='fadeOut')
    //-   h3(v-if="childWindow")
    //-     | Speaker Notes
    //-   h3(v-if="parentWindow")
    //-     | Presentation
    //-   h3(v-if="!childWindow && !parentWindow")
    //-     | Press P if you haven't
    //-   p.center(v-if="childWindow") We can have some fun in our parent window!
    //-   p.center(v-if="parentWindow") I'm doing a very serious talk right now
    //-   .center
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 2")
    //-         | Eagle.js is easy to use
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       h6(v-if="step >= 2 && childWindow")
    //-         | we can have a timer here: {{ slideTimer }}
    //-     eg-transition(enter='bounceInRight' leave='bounceOutRight')
    //-       p(v-if="step >= 3")
    //-         | Eagle.js has max hackability
    //-     eg-transition(enter='bounceInRight' leave='bounceOutRight')
    //-       h6(v-if="step >= 3 && childWindow")
    //-         | we can display the current slide index here: {{ currentSlideIndex }}
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 4")
    //-         | Eagle.js is modular
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       h6(v-if="step >= 4 && childWindow")
    //-         | we also could insert our notes here (duh)
    //-     eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 5")
    //-         | You can press P again to close child window

    //- slide(:steps=6, leave='fadeOut')
    //-   eg-transition(enter='flipInX')
    //-     h3 To use Presenter Mode
    //-   eg-transition(enter='flipInX')
    //-     eg-code-block(lang='html').
    //-       .eg-slideshow

    //-         slide
    //-           p Eagle.is is awesome!<eg-code-comment :active='step === 2' enter='flipInY'>This would always show up</eg-code-comment>
    //-           p(v-if="parentWindow") I can be a note!<eg-code-comment :active='step === 3' enter='flipInY'>This would only show on child window</eg-code-comment>
    //-           p(v-if="childWindow") I can be a note too!<eg-code-comment :active='step === 4' enter='flipInY'>This would only show on parent window</eg-code-comment>
    //-   eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 5")
    //-         | It might be counter-intuitive that '(v-if="parentWindow")' is acutually child window. It's because it means this window has a parent window, thus making itself a child window.
    //-   eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
    //-       p(v-if="step >= 6")
    //-         | But the good thing is that you can put notes in either parent window or child window, so it really doesn't matter!

    //- slide(enter='zoomIn', leave='fadeOut')
    //-   h3 That's all folks !
    //-   p.center Think you can help ?
    //-   .center
    //-     img.computerkid.shadowbox(src='https://i.imgur.com/AAlntwU.gif')
    //-   p.center.
    //-     I'm not a frontend person, so everyone<br />
    //-     is welcome to contribute to <a href="https://github.com/Zulko/eagle.js" target='_blank'> the repo</a>.

    slide(enter='fadeIn')
      h3 Thank you !
      p This slideshow's so fresh, it has end credits.
      end-credits(:username='username')
</template>


<script>
import eagle from 'eagle.js'

export default {
  mixins: [eagle.slideshow],
  infos: {
    title: 'Introducing Eagle.js',
    description: 'Watch this first if you are new to Eagle.js',
    path: 'introducing-eagle'
  },
  components: {
    'awesome-inserted-slide': require('./AwesomeInsertedSlide').default,
    'end-credits': require('./EndCredits').default
  },
  data: function () {
    return {
      username: 'Tracy',
      preference: 'baby bunnies',
      preferences: [
        {
          label: 'baby bunnies',
          text: 'Baby bunnies'
        },
        {
          label: 'fluffy puppies',
          text: 'Fluffy puppies'
        },
        {
          label: 'funny kitties',
          text: 'Funny kitties'
        }
      ],
      slideCategories: {
        themes: {
          show: true,
          name: 'Theming'
        },
        slideReuse: {
          show: true,
          name: 'Slide reuse'
        },
        interactivity: {
          show: true,
          name: 'Interactivity'
        }
      },
      preloadedImages: {
        computerKid: 'https://i.imgur.com/AAlntwU.gif',
        youRightNow: 'https://i.imgur.com/DFBTj0a.gif',
        bretagne: 'https://i.imgur.com/rYkJ6I8.jpg',
        forrestRoad: 'https://i.imgur.com/hxTMFZW.jpg',
        starrySky: 'https://i.imgur.com/yO2ivoD.jpg',
        cityBokeh: 'https://i.imgur.com/kmmHith.jpg',
        darkWoods: 'https://i.imgur.com/FL9mwpd.jpg',
        pushButton: 'https://i.imgur.com/KaAyvZ5.gif'
      }
    }
  },
  methods: {
    message: function (name) {
      return {
        'baby bunnies': 'Yeeeeah my favorite too !',
        'fluffy puppies': 'Wow so original.',
        'funny kitties': 'Good for you ' + this.username + '.',
        'Theming': 'Ok ' + this.username + ', whatever.',
        'Slide reuse': 'Seriously ' + this.username + ' you <em>want</em> to see this.',
        'Interactivity': 'Well that\'s this slide, ' + this.username +
                         '. <br /> A bit too late to unsee it, heh ?'
      }[name]
    }
  }
}
</script>

<style lang='scss'>
@import 'node_modules/eagle.js/dist/themes/agrume/agrume';
#IntroducingEagle {
  .frontpage {
    img {
      height: 7em;
    }
    img.control-schema {
      width: 8em;
      height: 3em;
    }
  }
  .heart {
    width: 1em;
    height: 0.8em;
    margin-left: 0.1em;
    margin-right: 0.1em;
    background-image: url('./assets/heart.svg');
    background-position: center center;
    background-repeat:  no-repeat;
    background-size: contain;
  }

  .quarter {
    text-align: center;
    p {
      margin-top: 0;
      text-align: center;
    }
    h4 {
      margin-top: 0;
      margin-bottom: 0
    }
  }
  .boredYet {
    p {
      margin-bottom: 0.3em;
      margin-top: 1.3em;
    }
    .button {
      border: none;
    }
    .button.prev {
      float: left;
    }
    .button.next {
      float: right;
    }
  }
  img.computerkid {
    height: 6.5em;
  }

  a {
    color: black;
  }

  .parentWindow {
    border: solide 1px red;
  }
}
</style>