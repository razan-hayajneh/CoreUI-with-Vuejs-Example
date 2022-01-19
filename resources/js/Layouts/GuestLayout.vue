<template>
    <CNavbar expand="lg" color-scheme="dark" class="bg-primary">
    <CContainer fluid>
        <CNavbarBrand href="#">
            <CAvatar style="width:30px;height:30px" src="/images/browser_logo.jpg">CUI</CAvatar>
        </CNavbarBrand>
        <CNavbarToggler aria-label="Toggle navigation" aria-expanded={visible} @click="visible = !visible"/>
        <CCollapse class="navbar-collapse" :visible="visible">
            <CNavbarNav>
                <CNavItem class="hidden px-2 py-2 sm:block ">
                    <Link :href="route('welcome')" class="text-white no-underline">
                        Home
                    </Link>
                </CNavItem>
                <CDropdown variant="nav-item" :popper="false">
                    <CDropdownToggle CDropdownToggle color="secondary">Dropdown button</CDropdownToggle>
                    <CDropdownMenu>
                        <CDropdownItem href="#">Action</CDropdownItem>
                        <CDropdownItem href="#">Another action</CDropdownItem>
                        <CDropdownDivider />
                        <CDropdownItem href="#">Something else here</CDropdownItem>
                    </CDropdownMenu>
                </CDropdown>
                <CNavItem  class="hidden px-2 py-2 sm:block ">
                    <Link :href="route('contact')" class="text-white no-underline">
                        Contact us
                    </Link>
                </CNavItem>
                <CNavItem v-if="canLogin" class="hidden fixed top-0 right-0 px-6 py-2 sm:block">
                    <Link v-if="$page.props.user" :href="route('dashboard')" class="text-white no-underline">
                        Dashboard
                    </Link>
                    <CButtonGroup v-else>
                        <Link :href="route('login')" class="text-white no-underline">
                            Log in
                        </Link>
                        <Link v-if="canRegister" :href="route('register')" class="ml-4 text-white no-underline">
                            Register
                        </Link>
                    </CButtonGroup>
                </CNavItem>
            </CNavbarNav>
        </CCollapse>
    </CContainer>
    </CNavbar>
</template>
<script>
    import { defineComponent } from 'vue'
    import { Link } from '@inertiajs/inertia-vue3'

    export default defineComponent({
        name:"GuestLayout",
        components:{
            Link
        },
        props: {
            canLogin: {
                Type: Boolean,
                default: true
            },
            canRegister: {
                Type: Boolean,
                default: true
            },
        }
    })
</script>

