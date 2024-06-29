# Today I learned again: Disabled and Readonly

In HTML, boolean attributes such as disabled and readonly can only legally take the name of the attribute.

```html
<button disabled readonly>Benjamin</button>
```

is the equivalent to

```html
<button disabled="disabled" readonly="readonly">Benjamin</button>
```

Many browsers though accept any text as being affirmative. This means that the following tags will render a disabled button:

```html
<button disabled readonly>Benjamin</button>
<button disabled="disabled" readonly="readonly">Benjamin</button>
<button disabled="true" readonly="true">Benjamin</button>
<button disabled="false" readonly="false">Benjamin</button>

<button class='benjamin'>Benjamin</button>
<script>
  const benjaminButton = document.querySelector('.benjamin');
  benjaminButton.setAttribute('disabled', 'disabled');
  benjaminButton.setAttribute('readonly', 'readonly');
</script>
```

To effectively re-enable the button, the attribute needs to be removed

```html
<button>Benjamin</button>

<button class='benjamin'>Benjamin</button>
<script>
  const benjaminButton = document.querySelector('.benjamin');
  benjaminButton.removeAttribute('disabled');
  benjaminButton.removeAttribute('readonly');
</script>
```
