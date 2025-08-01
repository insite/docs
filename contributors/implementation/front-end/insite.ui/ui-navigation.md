---
description: >-
  Guidelines for implementing intuitive, consistent navigation throughout the
  platform
---

# UI Navigation

## Dynamic Breadcrumbs

### The problem

Our current screen implementation allows to bind it to the parent and builder the breadcrumb.\
Though sometimes the screen can be referenced by multiple other screens and we need to support the dynamic breadcrumbs.\
For example, the screen "Lock Survey's Response" can be referenced from "Response Search" page and "Response Outline" page.\
The proposed solution uses two new interfaces and the class **ReturnUrl**.

### The solution

1. The screen should implement two additional interfaces: **IOverridesParent** and **IHasParentLinkParameters**

```
    public partial class Lock : BaseScreenUserControl, IOverridesParent, IHasParentLinkParameters
    {
```

1. Implement methods **GetParent** and **GetParentLinkParameters**.\
   Below is an example from Lock.ascx screen

```
        WebRoute IOverridesParent.GetParent() =>
            GetParent();

        string IHasParentLinkParameters.GetParentLinkParameters(WebRoute parent) =>
            GetParentLinkParameters(parent, "panel=results");
```

Methods **GetParent** and **GetParentLinkParameters** are members of **BaseScreenUserControl** class.

1. If it is required to redirect back to the parent screen manually then **GetReturnUrl** method can be used

```
            CancelButton.NavigateUrl = GetReturnUrl("panel=results");
```

1. When it is needed to generate the link with "return url" then the class **ReturnUrl** can be used.\
   Below is an example from Responses/Outline.ascx

```
            LockLink.NavigateUrl = new ReturnUrl($"session={queryString.Session}")
                .GetRedirectUrl($"/admin/surveys2/responses/lock?session={queryString.Session}");
            UnlockLink.NavigateUrl = new ReturnUrl($"session={queryString.Session}")
                .GetRedirectUrl($"/admin/surveys2/responses/unlock?session={queryString.Session}");
```

### Notes

1. The approach is changed in Shift.UI project