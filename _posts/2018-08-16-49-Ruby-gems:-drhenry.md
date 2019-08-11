---
layout: post #
title: 49 Ruby gems drhenry # Generat automàticament
date: 2018-08-16 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

La gema de Ruby `drhenry` és una d'aquestes utilitats que si utilitzes **Jekyll** sovint no has de desconèixer, ja que automatitza l'escriptura de posts.

Tenim accés al codi de la gema al GitHub de [JuanjoSalvador](https://github.com/JuanjoSalvador/drhenry), el seu autor.


Podem instal·lar aquesta gema així:

```ruby
gem install drhenry
```

Depenent de la nostra instal·lació la podrem trobar en un lloc. Si instal·lem [RVM](https://rvm.io/), la trobarem ací:

```bash
/home/user/.rvm/gems/ruby-2.4.0/gems/drhenry-0.4.0/
```

En cas d'utilitzar `ruby` amb el paquet compilat per **Ubuntu 18.04**, el trobarem ací:

```bash
/var/lib/gems/2.5.0/gems/drhenry-0.4.0/
```

A aquest directori trobarem altres dos directoris: `bin` i `lib`.

Dins del directori `bin` tenim l'arxiu `drhenry` amb aquest contingut:

```ruby
#!/usr/bin/env ruby

require 'drhenrypost'

  post = DrHenryPost.new

	name  = post.name
	date  = post.date
	title = post.title(name)

  	post.create(date, name, title)
```

Al directori `lib` trobarem aquest contingut, el qual he modificat adaptant-lo a les meues necessitats:

```ruby
class DrHenryPost

  # Gets today's date
  def date
    time = Time.new
    date = time.strftime("%Y-%m-%d")
    return date.to_s
  end

  # Sets post filename
  def name
    string = []

    if ARGV.empty?
      puts "You have not provided a title for the post. Please introduce a title."
      print "> "
      STDOUT.flush
      joinName = gets.chomp
	nameArray = joinName.split(' ')
	  nameArray.each do |s|
	    string.push(s)
	  end
    else
      ARGV.each do |a|
        string.push(a)
      end
    end

    joinName = string.join('-')
    return joinName
  end

  # Sets post title (into the file)
  def title(postName)
    return postName.tr('-', ' ')
  end

  # Creates the file
  def create(date, filename, title)
    output = File.new("#{date}-#{filename}.md", "w")
    output.puts("---")
    output.puts("layout: post #")
    output.puts("title: " + "#{title}" + " # Generat automàticament")
    output.puts("date: " + "#{date}" + " # Data")
    output.puts("description: " + " # Argument")
    output.puts("keywords: " + " # Paraules clau")
    output.puts("coments: " +  " # Comentaris")
    output.puts("---")
    output.close
  end

end
```

Així, en escriure un nou post seguisc aquesta rutina:

1. Primer en situen en el directori `cd _post`
2. Escric el nom de l'arxiu: `drhenry 49 Ruby gem: drhenry`
3. Edite l'arxiu `vim 49` i polse el tabulador, el qual em torna aquest a línia: `2018-08-16-49-Ruby-gems:-drhenry.md`
4. En obrir l'arxiu em trobe amb aquest contingut:

```ruby
---
layout: post #
title: 49 Ruby gems: drhenry # Generat automàticament
date: 2018-08-16 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---
```

Sols queda editar els camps que vullguem i guardar.


### Clonant la configuració

Podem clonar la configuració des d'ací:

[Repositori](https://github.com/inclusa/drhenry)

El cas és que la configuració adaptada que utilitze roman al directori ``

Podem baixar l'arxiu de configuració al directori `/var/lib/gems/2.5.0/gems/drhenry-0.4.0/lib/` així:

```bash
sudo wget https://raw.githubusercontent.com/inclusa/drhenry/master/versions/inclusa/lib/drhenrypost.rb -O /var/lib/gems/2.5.0/gems/drhenry-0.4.0/lib/
```

### Mac OS X ###

El directori on es guarden les gemes per editar-les, segons versió, a Mac OS X és aquest:

```bash
cd /Library/Ruby/Gems/2.3.0/gems/
```

Fem notar que la ruta està referida a la versió `2.3.0` de les gemes de Ruby.
