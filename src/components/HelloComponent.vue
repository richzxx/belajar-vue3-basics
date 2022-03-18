<template>
    <h1 class="text-2xl" :title="message">First Paragraph : {{ msg }}</h1>
    <div class="text-justify mt-3 first-letter:text-2xl">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore explicabo praesentium asperiores et, quisquam ipsum quidem repellendus aspernatur dolorum? Delectus quas placeat amet eveniet, quia libero, nulla hic earum vel dicta, facere suscipit incidunt? Magnam maxime amet voluptatem optio. Magni perspiciatis impedit esse incidunt dolorem iste? Quis voluptate fuga deserunt.</p>
    </div>
</template>

<script>
export default {
    name: 'HelloComponent',
    props: {
        msg: String
    },
    data() {
        return {
            message: "Author"
        }
    },
}
</script>