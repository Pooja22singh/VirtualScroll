# Virtual Scrolling

If you have a large datset that includes more than hundred thousand items, 
And they get added to your DOM, every time in batches as soon as the user scrolls
to the end of the current viewport.


**Issues**


# Memory Usage:
With a large number of elements, the memory usage can become significant, leading to potential memory leaks or crashes, especially on devices with limited resources.

# Reflow and Repaint:

Browsers need to perform reflow and repaint operations to render changes. With many elements, these operations become more costly, leading to slower performance and laggy interactions.

# Event Handling:

Attaching event listeners to a large number of elements can also degrade performance. Browsers have to manage more events, which can slow down response times.
# Layout Calculations:

Complex layouts with many elements can increase the time required for layout calculations, making the page less responsive. so if meanwhile user tries to interact, the response can be very slow and scrolling will become sluggish.

When new elements are added dynamically at the bottom of a scrollable container, browsers generally perform reflow and repaint operations to adjust the layout and update the visual display. These operations ensure that the new content integrates seamlessly into the existing document structure and is visible to the user

Large elements or elements with complex CSS properties can increase the time required for these layout calculations, leading to delays in rendering updates and sluggish scrolling.
Excessive memory usage can lead to slower performance and potentially cause the browser to become unresponsive, especially on devices with limited resources (like mobile devices)

Although
Browsers leverage hardware acceleration (using the GPU) to improve rendering performance, especially for complex graphical tasks.
However, if the GPU is overwhelmed by large or numerous elements, or if hardware acceleration is not supported or optimized, scrolling performance can suffer. 

Hence the need of Virtual scroll.

# When exactly you should look for implementing virtual scroll

Implementing virtual scrolling typically becomes beneficial when dealing with a large number of items in a list or grid, where the total number of items exceeds what can be comfortably rendered within the viewport at once. The threshold where virtual scrolling starts to make sense can vary based on factors like the complexity of each item, device performance, and user experience expectations. Here are some considerations:

1. Large Number of Items: If your list or grid contains hundreds or thousands of items (e.g., more than 100), virtual scrolling can help optimize performance by rendering only the visible portion of items.

2. Device and Browser Performance: Lower-powered devices or older browsers may struggle with rendering large DOM structures efficiently. Virtual scrolling reduces the strain on resources by managing DOM elements dynamically.

3. Smooth User Experience: Even with fewer items (e.g., 100-200), if scrolling performance is impacted due to the complexity of each item (such as containing images, complex CSS, or interactive elements), implementing virtual scrolling can provide a smoother user experience.

4. Thresholds to Consider:
Less than 100 items: In general, if your list or grid consistently contains fewer than 100 items and scrolling performance is acceptable on a variety of devices and browsers, virtual scrolling may not be necessary.

    100-200 items: Once you approach or exceed 100 items, especially if these items are complex or include media (images, videos), you may start to notice performance impacts on lower-end devices. This is      a good range to consider implementing virtual scrolling to maintain responsiveness.

   More than 200 items: If your list or grid regularly contains more than 200 items, or if you anticipate scalability to this level, virtual scrolling becomes increasingly beneficial to manage DOM size and    improve scrolling performance.

5. Implementation Considerations:
User Interaction: Virtual scrolling should not compromise user experience. Users should still be able to scroll smoothly, and items should load dynamically as needed without noticeable delays.

6. Testing and Optimization: Measure performance on different devices and browsers to determine when virtual scrolling becomes necessary. Use performance profiling tools to identify bottlenecks and optimize accordingly.
