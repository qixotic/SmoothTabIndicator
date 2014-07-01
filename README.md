# Android SmoothTabIndicator

This project is forked from Andreas Stuetz's [PagerSlidingTabStrip](https://github.com/astuetz/PagerSlidingTabStrip) project. What I've done is adding some smooth transition effects to the text and icon indicators in the tab bar. The current sliding strip in apps like Google Play Store looks well, but the texts in the tab bar are of the same color and don't respond to user's scroll gesture, which can be further improved.


You may download the demo here [on the Play Store](https://play.google.com/store/apps/details?id=com.astuetz.viewpager.extensions.sample).

<img width="320" src="http://i.imgur.com/ragfOnm.gif" />
<img width="320" src="http://i.imgur.com/CslJhOD.gif" />


# Usage

The usage of this project is almost the same as the original [PagerSlidingTabStrip](https://github.com/astuetz/PagerSlidingTabStrip) project. Except that I'm not familiar with gradle, so if you are using eclipse or ADT as your building tool, just like me, you may need to download the code, import the project from `library/` folder as a library project and use this project as library in your own project.

If gradle is your only building tool, you may refer to the "sample" project in the `sample/` folder, which simply added the following code to the build script:

    dependencies {
        compile project(':library')
    }

You may also need to download the source code first. Sorry for the inconvenience. I'm learning gradle recently, and will update the usage ASAP.

**For your convenience, here is the usage from the original [PagerSlidingTabStrip](https://github.com/astuetz/PagerSlidingTabStrip) project:**

*For a working implementation of this project see the `sample/` folder.*

  1. Include the library as local library project or add the dependency in your build.gradle.
        
        dependencies {
            compile 'com.astuetz:pagerslidingtabstrip:1.0.1'
        }

  2. Include the PagerSlidingTabStrip widget in your layout. This should usually be placed
     above the `ViewPager` it represents.

        <com.astuetz.PagerSlidingTabStrip
            android:id="@+id/tabs"
            android:layout_width="match_parent"
            android:layout_height="48dip" />

  3. In your `onCreate` method (or `onCreateView` for a fragment), bind the
     widget to the `ViewPager`.

         // Initialize the ViewPager and set an adapter
         ViewPager pager = (ViewPager) findViewById(R.id.pager);
         pager.setAdapter(new TestAdapter(getSupportFragmentManager()));
         
         // Bind the tabs to the ViewPager
         PagerSlidingTabStrip tabs = (PagerSlidingTabStrip) findViewById(R.id.tabs);
         tabs.setViewPager(pager);

  4. *(Optional)* If you use an `OnPageChangeListener` with your view pager
     you should set it in the widget rather than on the pager directly.

         // continued from above
         tabs.setOnPageChangeListener(mPageChangeListener);

# Customization

To not just look like another Play Store styled app, go and adjust these values to match
your brand:

 * `pstsIndicatorColor` Color of the sliding indicator
 * `pstsUnderlineColor` Color of the full-width line on the bottom of the view
 * `pstsDividerColor` Color of the dividers between tabs
 * `pstsIndicatorHeight`Height of the sliding indicator
 * `pstsUnderlineHeight` Height of the full-width line on the bottom of the view
 * `pstsDividerPadding` Top and bottom padding of the dividers
 * `pstsTabPaddingLeftRight` Left and right padding of each tab
 * `pstsScrollOffset` Scroll offset of the selected tab
 * `pstsTabBackground` Background drawable of each tab, should be a StateListDrawable
 * `pstsShouldExpand` If set to true, each tab is given the same weight, default false
 * `pstsTextAllCaps` If true, all tab titles will be upper case, default true

*All attributes have their respective getters and setters to change them at runtime*

# Developed By

 * [Sida Wang](https://plus.google.com/109139605868523362059)


### Credits

 * [Andreas Stuetz](andreas.stuetz@gmail.com) - Author of [PagerSlidingTabStrip](https://github.com/astuetz/PagerSlidingTabStrip)

# License

    Copyright 2014 Sida Wang

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
