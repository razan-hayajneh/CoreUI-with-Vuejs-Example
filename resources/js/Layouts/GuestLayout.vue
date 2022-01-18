<template>
    <CNavbar expand="lg" color-scheme="dark" class="bg-primary">
    <CContainer fluid>
        <CNavbarBrand href="#">
            <CAvatar style="width:30px;height:30px" src="/images/browser_logo.jpg">CUI</CAvatar>
        </CNavbarBrand>
        <CNavbarToggler aria-label="Toggle navigation" aria-expanded={visible} @click="visible = !visible"/>
        <CCollapse class="navbar-collapse" :visible="visible">
            <CNavbarNav>
                <CNavItem>
                    <CNavLink href="/" active>
                        Home
                    </CNavLink>
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
                <CNavItem v-if="canLogin" class="hidden fixed top-0 right-0 px-6 py-2 sm:block">
                    <CNavLink v-if="$page.props.user" :href="route('dashboard')" class="text-sm text-white underline">
                        Dashboard
                    </CNavLink>
                    <CButtonGroup v-else>
                        <CNavLink :href="route('login')" class="text-sm text-white underline">
                            Log in
                        </CNavLink>
                        <CNavLink v-if="canRegister" :href="route('register')" class="ml-4 text-sm text-white underline">
                            Register
                        </CNavLink>
                    </CButtonGroup>
                </CNavItem>
            </CNavbarNav>
        </CCollapse>
    </CContainer>
    </CNavbar>
</template>
<script>
    import { defineComponent } from 'vue'

    export default defineComponent({
        name:"GuestLayout",
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

