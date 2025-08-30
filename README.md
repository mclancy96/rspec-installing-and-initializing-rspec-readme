# RSpec: Installing and Initializing RSpec

Welcome to Lesson 2! If Lesson 1 was about why testing matters, this lesson is all about rolling up your sleeves and getting RSpec set up in your own Ruby project. Don’t worry—this is easier than assembling IKEA furniture, and you won’t need an Allen wrench!

---

## Why Do We Need to Install RSpec?

Imagine you’re about to bake a cake. You wouldn’t start without flour, right? RSpec is the “flour” of your testing kitchen. Before you can write and run tests, you need to have RSpec available in your project.

## Step 1: Add RSpec to Your Project

If you’re working on a Ruby project (not Rails), open your project folder and find the `Gemfile`. If you don’t have a `Gemfile`, create one! Then add this line:

```ruby
gem 'rspec'
```

If you’re using Rails, you’ll want:

```ruby
# Gemfile
gem 'rspec-rails'
```

**Note:** For Rails projects, after installing the gem, you’ll also need to run:

```zsh
rails generate rspec:install
```

For plain Ruby projects, just use `rspec --init` (see below). Rails projects require `rspec-rails` and the generator step to set up all the Rails-specific helpers and configuration.

Now, install the gem(s) by running:

```zsh
bundle install
```

## Step 2: Initialize RSpec

Once RSpec is installed, you need to set it up for your project. This is where the magic happens! In your terminal, run:

```zsh
rspec --init
```

This command creates two important files:

- `.rspec` (a hidden file that configures how RSpec runs)
- `spec/spec_helper.rb` (a Ruby file where you can set up your test environment)

### What’s in These Files?

- **.rspec**: Think of this as RSpec’s “settings menu.” It tells RSpec how to behave when you run your tests. For example, it can make your test output colorful and easy to read (because who doesn’t love a little color?).
- **spec/spec_helper.rb**: This is where you can require libraries, set up configuration, and do any prep work your tests need. It’s like the backstage crew at a play—essential, but you don’t always see it.

#### Example: What You’ll See

After running `rspec --init`, your project will look like this:

```zsh
my_project/
  Gemfile
  .rspec
  spec/
    spec_helper.rb
```

And your `.rspec` file might look like:

```zsh
# .rspec
--require spec_helper
--format documentation
--color
```

## Step 3: Run the Test Suite (Even If It’s Empty!)

Let’s try running RSpec, even though we haven’t written any tests yet. In your terminal, type:

```zsh
# Terminal
rspec
```

You’ll see output like this:

```zsh
No examples found.

Finished in 0.00012 seconds (files took 0.12345 seconds to load)
0 examples, 0 failures
```

That’s RSpec’s way of saying, “I’m ready! Give me some tests!”

## Why Bother Running an Empty Suite?

It’s a great way to check that everything is set up correctly. If you see errors, double-check your Gemfile and make sure you ran `bundle install` and `rspec --init`.

## Common Pitfalls (and How to Avoid Them)

- **Forgot to run `bundle install`?** RSpec won’t be available. Always install your gems!
- **Didn’t run `rspec --init`?** You won’t have the `.rspec` or `spec_helper.rb` files. Rerun the command.
- **Accidentally deleted `spec_helper.rb`?** No worries—just run `rspec --init` again.

## Practice Prompts

1. Add RSpec to a new or existing Ruby project. What files get created? (Use file path comments in your examples!)
2. Try running `rspec` before and after adding a test file. What changes? Add a minimal test (even just `expect(true).to eq(true)`) so you can see an example being run and get feedback from RSpec.
3. Open `.rspec` and `spec/spec_helper.rb` in your editor. What do you notice? Add a file path comment at the top of each file for practice.
4. If you run into an error, what steps can you take to troubleshoot?

---

## Resources

- [Official RSpec Installation Guide](https://relishapp.com/rspec/rspec-core/v/3-10/docs/gettingstarted)
- [RSpec GitHub Repository](https://github.com/rspec/rspec)
- [RubyGems: rspec](https://rubygems.org/gems/rspec)

---

## What's Next?

Next: Lab 1 follows this lesson! In Lab 1, you’ll write your very first `describe`/`it`/`expect` specs against a simple Ruby class, such as a Calculator. This lab will let you apply your setup knowledge immediately and see RSpec in action, running your first passing and failing tests.
