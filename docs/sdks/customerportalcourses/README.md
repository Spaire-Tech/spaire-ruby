# CustomerPortal.CustomerPortalCourses

## Overview

### Available Operations

* [list_enrolled_courses](#list_enrolled_courses) - List Enrolled Courses
* [get_enrolled_course](#get_enrolled_course) - Get Enrolled Course
* [submit_quiz_attempt](#submit_quiz_attempt) - Submit Quiz Attempt
* [mint_lesson_playback_url](#mint_lesson_playback_url) - Mint Lesson Playback URL
* [mark_lesson_complete](#mark_lesson_complete) - Mark Lesson Complete
* [get_course_progress](#get_course_progress) - Get Course Progress
* [get_course_landing](#get_course_landing) - Get Course Landing Page
* [get_course_landing_by_product](#get_course_landing_by_product) - Get Course Landing Page by Product
* [check_lesson_access](#check_lesson_access) - Check Lesson Access
* [list_lesson_comments](#list_lesson_comments) - List Lesson Comments
* [create_lesson_comment](#create_lesson_comment) - Create Lesson Comment
* [delete_lesson_comment](#delete_lesson_comment) - Delete Lesson Comment
* [list_course_notes](#list_course_notes) - List All Notes for Course
* [upsert_lesson_note](#upsert_lesson_note) - Upsert Lesson Note
* [delete_lesson_note](#delete_lesson_note) - Delete Lesson Note

## list_enrolled_courses

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:list_enrolled_courses" method="get" path="/v1/customer-portal/courses/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.list_enrolled_courses(security: Models::Operations::CustomerPortalCustomerPortalCoursesListEnrolledCoursesSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.response_customer_portal_customer_portal_courses_list_enrolled_courses.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                       | Type                                                                                                                                                                            | Required                                                                                                                                                                        | Description                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                      | [Models::Operations::CustomerPortalCustomerPortalCoursesListEnrolledCoursesSecurity](../../models/operations/customerportalcustomerportalcourseslistenrolledcoursessecurity.md) | :heavy_check_mark:                                                                                                                                                              | The security requirements to use for the request.                                                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesListEnrolledCoursesResponse)](../../models/operations/customerportalcustomerportalcourseslistenrolledcoursesresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_enrolled_course

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:get_enrolled_course" method="get" path="/v1/customer-portal/courses/{course_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.get_enrolled_course(security: Models::Operations::CustomerPortalCustomerPortalCoursesGetEnrolledCourseSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: 'e9c5c2a0-5829-4a61-8ab0-55e843213527')

unless res.response_customer_portal_customer_portal_courses_get_enrolled_course.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                   | Type                                                                                                                                                                        | Required                                                                                                                                                                    | Description                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                  | [Models::Operations::CustomerPortalCustomerPortalCoursesGetEnrolledCourseSecurity](../../models/operations/customerportalcustomerportalcoursesgetenrolledcoursesecurity.md) | :heavy_check_mark:                                                                                                                                                          | The security requirements to use for the request.                                                                                                                           |
| `course_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesGetEnrolledCourseResponse)](../../models/operations/customerportalcustomerportalcoursesgetenrolledcourseresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## submit_quiz_attempt

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:submit_quiz_attempt" method="post" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/quiz-attempt" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.submit_quiz_attempt(security: Models::Operations::CustomerPortalCustomerPortalCoursesSubmitQuizAttemptSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '73e2ab1a-6c6f-43c3-8356-4674c5b1a32a', lesson_id: '3b167bc7-f952-44b9-a198-01c7f356fdaa', body: Models::Components::QuizAttemptSubmission.new(
  answers: []
))

unless res.quiz_attempt_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                   | Type                                                                                                                                                                        | Required                                                                                                                                                                    | Description                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                  | [Models::Operations::CustomerPortalCustomerPortalCoursesSubmitQuizAttemptSecurity](../../models/operations/customerportalcustomerportalcoursessubmitquizattemptsecurity.md) | :heavy_check_mark:                                                                                                                                                          | The security requirements to use for the request.                                                                                                                           |
| `course_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |
| `lesson_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |
| `body`                                                                                                                                                                      | [Models::Components::QuizAttemptSubmission](../../models/shared/quizattemptsubmission.md)                                                                                   | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesSubmitQuizAttemptResponse)](../../models/operations/customerportalcustomerportalcoursessubmitquizattemptresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## mint_lesson_playback_url

Authorize and mint a signed Mux playback URL for the lesson.

The client should call this endpoint each time it starts video
playback. Doing so records one view against the course owner's
monthly video-view quota. When the org has exhausted its quota,
this endpoint returns 402 and no playback URL is issued — the
customer sees an explanatory message instead of the video.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:mint_lesson_playback_url" method="post" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/playback-url" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.mint_lesson_playback_url(security: Models::Operations::CustomerPortalCustomerPortalCoursesMintLessonPlaybackUrlSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '17e9d5b6-9a99-481e-906a-97a63b2a1d55', lesson_id: '6f60753f-3c0c-49d4-9ebe-46546035dc62')

unless res.response_customer_portal_customer_portal_courses_mint_lesson_playback_url.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                           | Type                                                                                                                                                                                | Required                                                                                                                                                                            | Description                                                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                          | [Models::Operations::CustomerPortalCustomerPortalCoursesMintLessonPlaybackUrlSecurity](../../models/operations/customerportalcustomerportalcoursesmintlessonplaybackurlsecurity.md) | :heavy_check_mark:                                                                                                                                                                  | The security requirements to use for the request.                                                                                                                                   |
| `course_id`                                                                                                                                                                         | *::String*                                                                                                                                                                          | :heavy_check_mark:                                                                                                                                                                  | N/A                                                                                                                                                                                 |
| `lesson_id`                                                                                                                                                                         | *::String*                                                                                                                                                                          | :heavy_check_mark:                                                                                                                                                                  | N/A                                                                                                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesMintLessonPlaybackUrlResponse)](../../models/operations/customerportalcustomerportalcoursesmintlessonplaybackurlresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## mark_lesson_complete

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:mark_lesson_complete" method="post" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/complete" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.mark_lesson_complete(security: Models::Operations::CustomerPortalCustomerPortalCoursesMarkLessonCompleteSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '2d6587d5-a241-42d7-9537-d9a3636bda80', lesson_id: '0e1d8490-d280-4eb7-a500-044c4d22938e')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                     | Type                                                                                                                                                                          | Required                                                                                                                                                                      | Description                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                    | [Models::Operations::CustomerPortalCustomerPortalCoursesMarkLessonCompleteSecurity](../../models/operations/customerportalcustomerportalcoursesmarklessoncompletesecurity.md) | :heavy_check_mark:                                                                                                                                                            | The security requirements to use for the request.                                                                                                                             |
| `course_id`                                                                                                                                                                   | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |
| `lesson_id`                                                                                                                                                                   | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesMarkLessonCompleteResponse)](../../models/operations/customerportalcustomerportalcoursesmarklessoncompleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_course_progress

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:get_course_progress" method="get" path="/v1/customer-portal/courses/{course_id}/progress" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.get_course_progress(security: Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseProgressSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '3fe5c667-8964-460f-98d5-ebe0d038b675')

unless res.course_progress_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                   | Type                                                                                                                                                                        | Required                                                                                                                                                                    | Description                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                  | [Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseProgressSecurity](../../models/operations/customerportalcustomerportalcoursesgetcourseprogresssecurity.md) | :heavy_check_mark:                                                                                                                                                          | The security requirements to use for the request.                                                                                                                           |
| `course_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseProgressResponse)](../../models/operations/customerportalcustomerportalcoursesgetcourseprogressresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_course_landing

Get course landing page data with public lesson list.

This endpoint is used for both authenticated and unauthenticated users.
For enrolled users, includes all lessons (with gating status).
For non-enrolled users (or anonymous visitors), includes only free
preview lessons.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:get_course_landing" method="get" path="/v1/customer-portal/courses/{course_id}/landing" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.get_course_landing(security: Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '263dfc69-0ef8-4886-bb01-80f12ea707a0')

unless res.response_customer_portal_customer_portal_courses_get_course_landing.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                 | Type                                                                                                                                                                      | Required                                                                                                                                                                  | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                | [Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingSecurity](../../models/operations/customerportalcustomerportalcoursesgetcourselandingsecurity.md) | :heavy_check_mark:                                                                                                                                                        | The security requirements to use for the request.                                                                                                                         |
| `course_id`                                                                                                                                                               | *::String*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingResponse)](../../models/operations/customerportalcustomerportalcoursesgetcourselandingresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_course_landing_by_product

Public landing data for a course, looked up by its product id.

Mirrors `/courses/{course_id}/landing` but lets the public storefront
page resolve the course without first needing the course id.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:get_course_landing_by_product" method="get" path="/v1/customer-portal/courses/by-product/{product_id}/landing" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.get_course_landing_by_product(security: Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingByProductSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), product_id: 'c30fb729-8a95-4c59-a144-5a18f9daaf92')

unless res.response_customer_portal_customer_portal_courses_get_course_landing_by_product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                   | Type                                                                                                                                                                                        | Required                                                                                                                                                                                    | Description                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                                  | [Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingByProductSecurity](../../models/operations/customerportalcustomerportalcoursesgetcourselandingbyproductsecurity.md) | :heavy_check_mark:                                                                                                                                                                          | The security requirements to use for the request.                                                                                                                                           |
| `product_id`                                                                                                                                                                                | *::String*                                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                                          | N/A                                                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesGetCourseLandingByProductResponse)](../../models/operations/customerportalcustomerportalcoursesgetcourselandingbyproductresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## check_lesson_access

Check if the current user can access a lesson.

Returns { "can_access": bool, "reason": str, "locked_until": timestamp | null }
Reasons: "free" (is_free_preview), "enrolled" (has product), "paywall", "drip", "unpublished"

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:check_lesson_access" method="post" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/can-access" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.check_lesson_access(security: Models::Operations::CustomerPortalCustomerPortalCoursesCheckLessonAccessSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '5ff4eb74-b328-481e-92e0-722a4e2fa32d', lesson_id: 'cd9c0c32-3af9-4d5b-833d-e23277a06400')

unless res.response_customer_portal_customer_portal_courses_check_lesson_access.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                   | Type                                                                                                                                                                        | Required                                                                                                                                                                    | Description                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                  | [Models::Operations::CustomerPortalCustomerPortalCoursesCheckLessonAccessSecurity](../../models/operations/customerportalcustomerportalcourseschecklessonaccesssecurity.md) | :heavy_check_mark:                                                                                                                                                          | The security requirements to use for the request.                                                                                                                           |
| `course_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |
| `lesson_id`                                                                                                                                                                 | *::String*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                          | N/A                                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesCheckLessonAccessResponse)](../../models/operations/customerportalcustomerportalcourseschecklessonaccessresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_lesson_comments

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:list_lesson_comments" method="get" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.list_lesson_comments(security: Models::Operations::CustomerPortalCustomerPortalCoursesListLessonCommentsSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '4aad0495-0617-4cb1-adaa-36cc95cec77b', lesson_id: '5d447346-fd57-4110-84b8-650f99e1d55f')

unless res.response_customer_portal_customer_portal_courses_list_lesson_comments.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                     | Type                                                                                                                                                                          | Required                                                                                                                                                                      | Description                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                    | [Models::Operations::CustomerPortalCustomerPortalCoursesListLessonCommentsSecurity](../../models/operations/customerportalcustomerportalcourseslistlessoncommentssecurity.md) | :heavy_check_mark:                                                                                                                                                            | The security requirements to use for the request.                                                                                                                             |
| `course_id`                                                                                                                                                                   | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |
| `lesson_id`                                                                                                                                                                   | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesListLessonCommentsResponse)](../../models/operations/customerportalcustomerportalcourseslistlessoncommentsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_lesson_comment

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:create_lesson_comment" method="post" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.create_lesson_comment(security: Models::Operations::CustomerPortalCustomerPortalCoursesCreateLessonCommentSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: 'd3f379b4-ad3b-46f6-91f6-0a7a4752eda2', lesson_id: 'edfabd54-0b69-4b54-ad39-2f33ca938050', body: Models::Components::LessonCommentCreate.new(
  content: '<value>'
))

unless res.lesson_comment_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                       | Type                                                                                                                                                                            | Required                                                                                                                                                                        | Description                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                      | [Models::Operations::CustomerPortalCustomerPortalCoursesCreateLessonCommentSecurity](../../models/operations/customerportalcustomerportalcoursescreatelessoncommentsecurity.md) | :heavy_check_mark:                                                                                                                                                              | The security requirements to use for the request.                                                                                                                               |
| `course_id`                                                                                                                                                                     | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `lesson_id`                                                                                                                                                                     | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `body`                                                                                                                                                                          | [Models::Components::LessonCommentCreate](../../models/shared/lessoncommentcreate.md)                                                                                           | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesCreateLessonCommentResponse)](../../models/operations/customerportalcustomerportalcoursescreatelessoncommentresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_lesson_comment

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:delete_lesson_comment" method="delete" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/comments/{comment_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.delete_lesson_comment(security: Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonCommentSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '70a972f8-8dd4-49ea-8689-c10cde15258f', lesson_id: '3a2ada11-da6e-4303-8e43-e65ad159de87', comment_id: '7d01cfdc-232e-4016-833b-6087f2e47467')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                       | Type                                                                                                                                                                            | Required                                                                                                                                                                        | Description                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                      | [Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonCommentSecurity](../../models/operations/customerportalcustomerportalcoursesdeletelessoncommentsecurity.md) | :heavy_check_mark:                                                                                                                                                              | The security requirements to use for the request.                                                                                                                               |
| `course_id`                                                                                                                                                                     | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `lesson_id`                                                                                                                                                                     | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `comment_id`                                                                                                                                                                    | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonCommentResponse)](../../models/operations/customerportalcustomerportalcoursesdeletelessoncommentresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_course_notes

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:list_course_notes" method="get" path="/v1/customer-portal/courses/{course_id}/notes" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.list_course_notes(security: Models::Operations::CustomerPortalCustomerPortalCoursesListCourseNotesSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: 'b41e3867-1bf8-40f7-ab26-94bb53146aae')

unless res.response_customer_portal_customer_portal_courses_list_course_notes.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                              | [Models::Operations::CustomerPortalCustomerPortalCoursesListCourseNotesSecurity](../../models/operations/customerportalcustomerportalcourseslistcoursenotessecurity.md) | :heavy_check_mark:                                                                                                                                                      | The security requirements to use for the request.                                                                                                                       |
| `course_id`                                                                                                                                                             | *::String*                                                                                                                                                              | :heavy_check_mark:                                                                                                                                                      | N/A                                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesListCourseNotesResponse)](../../models/operations/customerportalcustomerportalcourseslistcoursenotesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## upsert_lesson_note

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:upsert_lesson_note" method="put" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/notes" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.upsert_lesson_note(security: Models::Operations::CustomerPortalCustomerPortalCoursesUpsertLessonNoteSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '13333c47-5821-4b9d-aa36-c6574a708bef', lesson_id: 'fb93fecc-3375-4183-a3f0-eef7c36cd0b4', body: Models::Components::CourseNoteUpsert.new(
  content: '<value>'
))

unless res.course_note_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                 | Type                                                                                                                                                                      | Required                                                                                                                                                                  | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                | [Models::Operations::CustomerPortalCustomerPortalCoursesUpsertLessonNoteSecurity](../../models/operations/customerportalcustomerportalcoursesupsertlessonnotesecurity.md) | :heavy_check_mark:                                                                                                                                                        | The security requirements to use for the request.                                                                                                                         |
| `course_id`                                                                                                                                                               | *::String*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `lesson_id`                                                                                                                                                               | *::String*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `body`                                                                                                                                                                    | [Models::Components::CourseNoteUpsert](../../models/shared/coursenoteupsert.md)                                                                                           | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesUpsertLessonNoteResponse)](../../models/operations/customerportalcustomerportalcoursesupsertlessonnoteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_lesson_note

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer_portal_courses:delete_lesson_note" method="delete" path="/v1/customer-portal/courses/{course_id}/lessons/{lesson_id}/notes" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_portal_courses.delete_lesson_note(security: Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonNoteSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: 'bc45e5b2-3fdc-4bc9-8f2e-6357f61366ee', lesson_id: '74f4c43f-ef88-4d4d-a749-1cf5ba81413a')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                 | Type                                                                                                                                                                      | Required                                                                                                                                                                  | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                | [Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonNoteSecurity](../../models/operations/customerportalcustomerportalcoursesdeletelessonnotesecurity.md) | :heavy_check_mark:                                                                                                                                                        | The security requirements to use for the request.                                                                                                                         |
| `course_id`                                                                                                                                                               | *::String*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `lesson_id`                                                                                                                                                               | *::String*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerPortalCoursesDeleteLessonNoteResponse)](../../models/operations/customerportalcustomerportalcoursesdeletelessonnoteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |