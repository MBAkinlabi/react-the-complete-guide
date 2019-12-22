# Understanding Single Page Applications and Multi Page Applications
- There are two kinds of applications
- Single page applications - only one HTML page - content is (re)rendered on Client
- Multi page applications - Multiple HTML Pages - Not all pages may be managed by React.
- Single Page application is the most popular for React apps and it's what the instructor would cover in this course.
- In this case, typically only one `ReactDOM.render()` call in the single page applications.
- In the multi page applications, we'll probably have different `ReactDOM.render()` calls. For example, you may have one `ReactDOM.render()` call per "widget"
- And even these widgets don't know of the existence of each other.