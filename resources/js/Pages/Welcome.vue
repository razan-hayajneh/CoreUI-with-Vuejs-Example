<template>
    <Head title="Welcome" />
    <GuestLayout :canLogin="canLogin" :canRegister="canRegister"></GuestLayout>
    <CCarousel controls indicators dark>
        <CCarouselItem >
            <a href="/">
                <CImage class="center"  src="/images/browser_logo.jpg" />
                <CCarouselCaption class="d-none d-md-block">
                <h5>First slide label</h5>
                <p>Some representative placeholder content for the first slide.</p>
                </CCarouselCaption>
            </a>
        </CCarouselItem>
        <CCarouselItem>
                <CImage class="center" src="/images/browser_logo.jpg" />
                <CCarouselCaption class="d-none d-md-block">
                <h5>First slide label</h5>
                <p>Some representative placeholder content for the first slide.</p>
                </CCarouselCaption>
        </CCarouselItem>
        <CCarouselItem>
                <CImage class="center" src="/images/browser_logo.jpg" />
                <CCarouselCaption class="d-none d-md-block rcorners3">
                <h5>First slide label</h5>
                <p>Some representative placeholder content for the first slide.</p>
                </CCarouselCaption>
        </CCarouselItem>
    </CCarousel>
    <CCardGroup>
        <CCard class="m-2 border-3">
            <CCardHeader class="text-center">Header</CCardHeader>
            <CImage  class="center" orientation="top" width="200" height="200"  src="/images/browser_logo.jpg" />
            <CCardBody>
            <CCardTitle>Card title</CCardTitle>
            <CCardText>This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</CCardText>
            <CCardText><small class="text-muted">Last updated 3 mins ago</small></CCardText>
            </CCardBody>
        </CCard>
        <CCard class="m-2 border-3">
            <CCardHeader class="text-center">Header</CCardHeader>
            <CImage  class="center" orientation="top" width="200" height="200" src="/images/browser_logo.jpg" />
            <CCardBody>
            <CCardTitle>Card title</CCardTitle>
            <CCardText>This card has supporting text below as a natural lead-in to additional content.</CCardText>
            <CCardText><small class="text-muted">Last updated 3 mins ago</small></CCardText>
            </CCardBody>
        </CCard>
        <CCard class="m-2 border-3">
            <CCardHeader class="text-center">Header</CCardHeader>
            <CImage  class="center" orientation="top" width="200" height="200" src="/images/browser_logo.jpg" />
            <CCardBody>
            <CCardTitle>Card title</CCardTitle>
            <CCardText>This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</CCardText>
            <CCardText><small class="text-muted">Last updated 3 mins ago</small></CCardText>
            </CCardBody>
        </CCard>
    </CCardGroup>
    <br/>
    <Footer></Footer>
</template>

<style scoped>
.rcorners3 {
  border-radius: 15px 50px;
  background: #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}
    .center {
        display: block;
        margin-left: auto;
        margin-right: auto;
        width: 50%;
    }
    .bg-gray-100 {
        background-color: #f7fafc;
        background-color: rgba(247, 250, 252, var(--tw-bg-opacity));
    }

    .border-gray-200 {
        border-color: #edf2f7;
        border-color: rgba(237, 242, 247, var(--tw-border-opacity));
    }

    .text-gray-400 {
        color: #cbd5e0;
        color: rgba(203, 213, 224, var(--tw-text-opacity));
    }

    .text-gray-500 {
        color: #a0aec0;
        color: rgba(160, 174, 192, var(--tw-text-opacity));
    }

    .text-gray-600 {
        color: #718096;
        color: rgba(113, 128, 150, var(--tw-text-opacity));
    }

    .text-gray-700 {
        color: #4a5568;
        color: rgba(74, 85, 104, var(--tw-text-opacity));
    }

    .text-gray-900 {
        color: #1a202c;
        color: rgba(26, 32, 44, var(--tw-text-opacity));
    }

    @media (prefers-color-scheme: dark) {
        .dark\:bg-gray-800 {
            background-color: #2d3748;
            background-color: rgba(45, 55, 72, var(--tw-bg-opacity));
        }

        .dark\:bg-gray-900 {
            background-color: #1a202c;
            background-color: rgba(26, 32, 44, var(--tw-bg-opacity));
        }

        .dark\:border-gray-700 {
            border-color: #4a5568;
            border-color: rgba(74, 85, 104, var(--tw-border-opacity));
        }

        .dark\:text-white {
            color: #fff;
            color: rgba(255, 255, 255, var(--tw-text-opacity));
        }

        .dark\:text-gray-400 {
            color: #cbd5e0;
            color: rgba(203, 213, 224, var(--tw-text-opacity));
        }
    }
</style>

<script>
    import { defineComponent } from 'vue'
    import { Head } from '@inertiajs/inertia-vue3'
    import GuestLayout from '@/Layouts/GuestLayout.vue'
    import Footer from '@/Components/Footer.vue'

    export default defineComponent({
        components: {
            Head,
            GuestLayout,
            Footer
        },
        props: {
            canLogin: Boolean,
            canRegister: Boolean
        }
    })
</script>
