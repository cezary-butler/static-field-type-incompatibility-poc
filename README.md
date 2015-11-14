# static-field-type-incompatibility-poc

## Goal
This project is to prove suspection that changing _public static final_ field type can break binary compatiblity with apps build against version with different type.
This occurs even when apps compile with both version of library (there is no explicit type incompatibility).

## How this presents
This error presents with:
`Exception in thread "main" java.lang.NoSuchFieldError: INSTANCE`

## Solution
If you have to deal with this kind of problem best way is to have fallback method using reflection.

## How to avoid it
Use more general types for _public static final_ fields when possible.
Use static accessor methods for constants.
