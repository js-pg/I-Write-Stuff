<script context="module">
    export function getLs(key) {
        return localStorage.getItem(key);
    }

    export function setLs(key, value) {
        localStorage.setItem(key, value);
    }

    export function removeLs(key) {
        localStorage.removeItem(key);
    }
</script>