<!-- <script lang="ts">
	import { onNavigate } from '$app/navigation';

function delayNavigation() {
    return new Promise((resolve) => setTimeout(resolve, 100));
}

onNavigate(async (navigation) => {
    if (!document.startViewTransition) {
        await delayNavigation();
        return;
    }

    return new Promise((resolve) => {
        document.startViewTransition(async () => {
        await delayNavigation();
        resolve();
        await navigation.complete;
        });
    });
});
</script> -->