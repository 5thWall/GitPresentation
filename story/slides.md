!SLIDE

# `<story>`

!SLIDE

# 2 students #

!SLIDE

# group project #

!SLIDE

# problem #

!SLIDE bullets incremental

# how to share code #

 * email
 * flash drives
 * shared folders

!SLIDE bullets incremental

# more problems #

 * who has what version
 * what did you change
 * how do we start over from working code

!SLIDE

# git #
## dropbox ##

!SLIDE

# Susan #

!SLIDE

    @@@ruby
    class Maze
      def initialize(x, y)
        @map = Array.new
        y.times { |i| @map[i] = ['#'] * x }
      end
    end

!SLIDE commandline incremental

    $ git init
    Initialized empty Git repository in /Users/Susan/ClassProject/.git/
    
    $ git add maze.rb
    
    $ git commit -m "First commit, woot"
    [master (root-commit) b793498] First commit, woot
	 1 files changed, 6 insertions(+), 0 deletions(-)
	 create mode 100644 maze.rb
	
!SLIDE

# sharing the code #

!SLIDE commandline incremental

    $ cd ~/Dropbox/shared
    
    $ git clone --bare ~/ClassProject
    Cloning into bare repository ClassProject.git...
	done.
	
	$ cd ~/ClassProject
	
	$ git remote add origin ~/Dropbox/shared/ClassProject.git
	
!SLIDE

# Tom #

!SLIDE commandline incremental

    $ git clone ~/Dropbox/shared/ClassProject.git
	Cloning into ClassProject...
	done.

!SLIDE

    @@@ruby
    def initialize(x = 30, y = 15)
      x = x >= 5 ? x : 5
	  x += 1 unless x % 2 != 0
      
	  y = y >= 5 ? y : 5
      y += 1 unless y % 2 != 0
    
      fill_in! x, y
      dig_out!
    end
    
    fill_in!(x, y)
      @map = Array.new
      y.times { |i| @map[i] = ['#'] * x }
    end

!SLIDE commandline incremental

    $ git status
    # On branch master
	# Changed but not updated:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   maze.rb
	
	$ git commit -am "Added validation and broke out some methods"
	[master b4066df] Added validation and broke out some methods
	 1 files changed, 12 insertions(+), 1 deletions(-)
	
!SLIDE

# pushing changes #

!SLIDE commandline incremental

	$ git pull origin master
	From /Users/Tom/Dropbox/shared/ClassProject.git
	 * branch            master     -> FETCH_HEAD
	Already up-to-date.
	
	$ git push origin master
	Counting objects: 5, done.
	Delta compression using up to 4 threads.
	Compressing objects: 100% (2/2), done.
	Writing objects: 100% (3/3), 446 bytes, done.
	Total 3 (delta 0), reused 0 (delta 0)
	Unpacking objects: 100% (3/3), done.
	To /Users/Tom/Dropbox/shared/ClassProject.git
	   b793498..b4066df  master -> master

!SLIDE

# merging #

!SLIDE  commandline incremental

    $ git pull origin master
	remote: Counting objects: 5, done.
	remote: Compressing objects: 100% (2/2), done.
	remote: Total 3 (delta 0), reused 0 (delta 0)
	Unpacking objects: 100% (3/3), done.
	From /Users/Susan/Dropbox/shared/ClassProject
	 * branch            master     -> FETCH_HEAD
	Auto-merging maze.rb
	CONFLICT (content): Merge conflict in maze.rb
	Automatic merge failed; fix conflicts and then commit the result.
	
!SLIDE commandline incremental

	$ git status
	# On branch master
	# Unmerged paths:
	#   (use "git add/rm <file>..." as appropriate to mark resolution)
	#
	#	both modified:      maze.rb
	#
	no changes added to commit (use "git add" and/or "git commit -a")
	
	$ git add maze.rb
	
	$ git commit -am "Merged with Tom's changes"
	[master 552ba36] Merged with Tom's changes

!SLIDE commandline incremental

    $ git pull origin master
	From /Users/Susan/Dropbox/shared/ClassProject
	 * branch            master     -> FETCH_HEAD
	Already up-to-date.
	
	$ git push origin master
	Counting objects: 10, done.
	Delta compression using up to 4 threads.
	Compressing objects: 100% (4/4), done.
	Writing objects: 100% (6/6), 1.01 KiB, done.
	Total 6 (delta 1), reused 0 (delta 0)
	Unpacking objects: 100% (6/6), done.
	To /Users/Susan/Dropbox/shared/ClassProject.git
	   b4066df..552ba36  master -> master
	
!SLIDE

# `</story>` #
