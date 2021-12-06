# animated-dollop

This template is based on jekyll, a static website generator. This template can be used to quickly setup a website, features include:

- Responsive layout
- Custom colors with variables 
- Responsive nav bar
- Easy documentation tab
- Search tab to filter blogs/posts
- Social media widgets

## Get Started 

### To run the template you need install Ruby,Bundler and Jekyll

1. Install Ruby & Bundler (as root):

   _Note: To become root, you must either run `su` or `sudo -s`_

   * **Fedora** / **RHEL** / **CentOS**:
     ```
     dnf install -y rubygem-bundler ruby-devel libffi-devel make gcc gcc-c++ \
     redhat-rpm-config zlib-devel libxml2-devel libxslt-devel tar nodejs
     ```
  
   * **Debian** / **Ubuntu**:
     ```
     apt update && apt install bundler zlib1g-dev
     ```

   * **macOS** / **OS X**:
   
     _Note: First, you must install Mac developer tools. Then, run the following:_
     
     ```
     gem update --system
     gem install bundler
     ```

2. Install gems (as user):
   ```
   bundle install
   ```

3. Run Jekyll:
   ```
   bundle exec jekyll server
   ```
   
## Styling

Styling is simple, this template uses SCSS and the files can be found in `/assets`
All the colors for Navbar, footer etc are defined in `/assets/variables.scss` - here the colors can be customized accordignly 

## Responsive Layout

This template is responsive on default setting,to change the behavior of website based on the screen size - in `/assets/` all the individual .scss files will have 
```
@mixin large {
  @media screen and (min-width: #{$large-breakpoint}) {
    @content;
  }
}

@mixin medium {
  @media screen and (min-width: #{$medium-breakpoint}) and (max-width: #{$large-breakpoint}) {
    @content;
  }
}

@mixin small {
  @media screen and (max-width: #{$medium-breakpoint}) {
    @content;
  }
}
```
The above css elements will define the behavior of each screen size. Large will define breakpoint for PCs, Medium for Tablet, and Small for Mobile devices.
An example for responsive css element can be found below 
```
.page-header {
  position: fixed;
  width: 100%;
  color: $header-heading-color;
  text-align: center;
  background-color: $header-bg-color;
  //background-image: linear-gradient(120deg, $header-bg-color-secondary, $header-bg-color);

  @include large {
    padding: 5rem 6rem;
  }

  @include medium {
    padding: 3rem 4rem;
  }

  @include small {
    padding: 2rem 1rem;
  }
}
```
