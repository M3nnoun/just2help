
## 📍 Get Latitude & Longitude from an Address in Google Sheets

### Step 1: Add the Custom Function

1. Open your Google Sheet  
2. Click **Extensions → Apps Script**  
3. Delete any existing code and paste this:

```javascript
function GETLAT(address) {
  var geocoder = Maps.newGeocoder().geocode(address);
  if (geocoder.results.length > 0) {
    return geocoder.results[0].geometry.location.lat;
  }
  return "";
}

function GETLNG(address) {
  var geocoder = Maps.newGeocoder().geocode(address);
  if (geocoder.results.length > 0) {
    return geocoder.results[0].geometry.location.lng;
  }
  return "";
}
````

4. Click **Save**

---

### Step 2: Use It in Your Sheet

If your address is in cell **A2**:

* Latitude:

```
=GETLAT(A2)
```

* Longitude:

```
=GETLNG(A2)
```

Drag the formulas down to apply to multiple addresses ✅

Done! 🎉

