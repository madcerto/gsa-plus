<script lang="ts">
import { Avatar, NavHamburger, Dropdown, DropdownHeader, DropdownGroup, DropdownItem } from "flowbite-svelte";

const { user } = $props();
</script>

<nav class="sticky top-0 p-2.5 px-16 bg-white border-b-1 border-gray flex flex-row justify-between shadow-sm">
    <a href="/" class="font-bold text-5xl font-serif text-primary-800">
        GSA+
    </a>
    <div class="flex items-center md:order-2">
        <Avatar id="avatar-menu" src={user.avatarImgUrl} class="hover:cursor-pointer h-12 w-12" />
        <NavHamburger />
    </div>
    <Dropdown placement="bottom" triggeredBy="#avatar-menu">
        <DropdownHeader>
            <span class="block text-sm">{user.fullName}</span>
            <span class="block truncate text-sm font-medium">abc123@drexel.edu</span>
        </DropdownHeader>
        <DropdownGroup>
            <DropdownItem>Attended Events</DropdownItem>
            <DropdownItem class="text-red">Sign out</DropdownItem>
        </DropdownGroup>
    </Dropdown>
</nav>
