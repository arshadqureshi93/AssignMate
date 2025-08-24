# AssignMate - Simple User Assignment for Frappe

A lightweight Frappe app that provides a simplified user assignment interface for when you need something straightforward and minimal.

## Why I Built This?

I built this app for my specific use case where I needed a different approach to user assignments. Frappe's built-in assignment system is powerful and feature-rich, but I wanted something simpler for my particular requirements where minimalism and straightforward functionality were more important than advanced features.

## 🚀 Features

- **Simple Multi-Select Interface**: Clean multi-user selection without Tab MultiSelect complexity
- **Simple Interface**: Clean UI without complexity
- **Multi-Doctype Support**: Works with Task, Issue, Project, etc.
- **API-Driven**: Fast and efficient performance
- **Easy Setup**: Just add a few lines of code
- **Permission Aware**: Respects user roles and permissions

## 📦 Installation

```bash
bench get-app https://github.com/arshadqureshi93/AssignMate.git
bench --site your-site.name install-app assignmate
```

## 🛠️ Usage & Examples
```bash
frappe.ui.form.on("Your Doctype", {
    refresh(frm) {
        if (!frm.doc.name || frm.doc.__islocal) return;
          frappe.require(["assets/assignmate/js/assignmate.js"], () => {
            if (window.setupUserAssignment) {
              window.setupUserAssignment(frm, "Your Doctype", frm.doc.name);
            }
        });
    }
});
```
## 🔧 Customization

You can easily customize by modifying:

assignmate/api.py - Backend logic

assignmate/public/js/assignmate.js - Frontend interface

assignmate/hooks.py - App configuration

## ❤️ Thanks
If you find this useful, feel free to use it in your projects! 
