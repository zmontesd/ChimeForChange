equalizer
=========

Module to define equality, equivalence and inspection methods

[![Gem Version](https://badge.fury.io/rb/equalizer.png)][gem]
[![Build Status](https://secure.travis-ci.org/dkubb/equalizer.png?branch=master)][travis]
[![Dependency Status](https://gemnasium.com/dkubb/equalizer.png)][gemnasium]
[![Code Climate](https://codeclimate.com/github/dkubb/equalizer.png)][codeclimate]
[![Coverage Status](https://coveralls.io/repos/dkubb/equalizer/badge.png?branch=master)][coveralls]

[gem]: https://rubygems.org/gems/equalizer
[travis]: https://travis-ci.org/dkubb/equalizer
[gemnasium]: https://gemnasium.com/dkubb/equalizer
[codeclimate]: https://codeclimate.com/github/dkubb/equalizer
[coveralls]: https://coveralls.io/r/dkubb/equalizer

Examples
--------

``` ruby
class GeoLocation
  include Equalizer.new(:latitude, :longitude)

  attr_reader :latitude, :longitude

  def initialize(latitude, longitude)
    @latitude, @longitude = latitude, longitude
  end
end

point_a = GeoLocation.new(1, 2)
point_b = GeoLocation.new(1, 2)
point_c = GeoLocation.new(2, 2)

point_a.inspect    # => "#<GeoLocation latitude=1 longitude=2>"

point_a == point_b           # => true
point_a.hash == point_b.hash # => true
point_a.eql?(point_b)        # => true
point_a.equal?(point_b)      # => false

point_a == point_c           # => false
point_a.hash == point_c.hash # => false
point_a.eql?(point_c)        # => false
point_a.equal?(point_c)      # => false
```

Credits
-------

* Dan Kubb ([dkubb](https://github.com/dkubb))
* Piotr Solnica ([solnic](https://github.com/solnic))
* Markus Schirp ([mbj](https://github.com/mbj))

Contributing
-------------

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

Copyright
---------

Copyright &copy; 2009-2013 Dan Kubb. See LICENSE for details.
