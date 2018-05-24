---

 title: RSpec & Algorithms

---

# RSpec Refresh

The approach to a [technical interview question](https://autumnj.github.io//technical-interviews/) is important, but more important than that is the preparation for it. In preparation, I’ve been using [Pramp](https://www.pramp.com/), [Codewars](https://www.codewars.com/), [Interview Cake](https://www.interviewcake.com/), and reading through [Code Complete](https://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670). Unfortunately, most interview prep platforms don’t allow you to write your own tests, so I expanded upon an existing algorithm [GitHub repo](https://github.com/AutumnJ/algorithm-practice/tree/master) to work through common algorithm problems in a variety of languages **and** practice writing tests.

Since I've been working in JavaScript recently. I decided to dive back into Ruby and [RSpec](http://rspec.info/), a Ruby library that allows programmers to describe behaviors and outcomes in more natural language. For my algorithm problem use case, it's a great testing framework. 


[This article](https://code.tutsplus.com/articles/rspec-testing-for-beginners-part-1--cms-26716) provides a great introduction to incorporating RSpec in a project. In terms of writing tests, RSpec, as with other testing frameworks, provides a pretty clear syntax, which is more pseudo-code than code. 

Below is an example of an RSpec test:

```ruby
describe "two_sum" do
  it "returns an empty array if given an empty array" do
    expect(two_sum([],3)).to eq([])
  end
  it "returns an array of two indices that sum to the target" do
    expect(two_sum([2, 7, 11, 15], 9)).to match_array([0,1])
    expect(two_sum([15,17,2,1,-3], 12)).to match_array([0,4])
    expect(two_sum([15,2,2,1,-3], 4)).to match_array([1,2])
  end
end
```


⋅⋅* The `describe` block indicates what is being tested, and takes a string as an argument.
⋅⋅* `describe` accepts a block, which begins with `do` and ends with `end`.
⋅⋅* Inside of the `do` block, there is an `it` block, which takes a string describing the desired outcome as its argument. While the string shouldn't be overly verbose, it also needs to be clear and concise so others can read and run tests, and write code to pass those tests with ease. *[Better Specs](http://www.betterspecs.org/) provides great insight on improving test descriptions.* 
⋅⋅* `it` also accepts a block that begins with `do` and ends with `end`.
⋅⋅* Within the `do` block that follows `it`, `expect` is used to feed the test a variable or argument for it run against the written code. `⋅⋅* expect` is chained with the expectation, indicated by `.to`. Often, `.to` is used with equal or not equal (`.to eq` or `.not_to eq`). But there are a variety of [expecation methods](https://rspec.info/documentation/3.5/rspec-expectations/method_list.html) that can be chained to indicate the expected outcome more clearly.

Great tests adequately address potential edge cases. Using the two sum test above as an example, if the test didn't incorporate negative integers and an empty array, it's possible someone would write a solution that would pass the tests but would fail when those edge cases were incorporated. When writing one's own tests and solutions, it's important to adequately evaluate edge cases and include those in the tests. 

As my coding skills have grown, so have my cat friends:

![alt text](/assets/images/IMG_0384.jpeg "Meow!")