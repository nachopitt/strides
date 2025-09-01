<script setup>
import { Link } from '@inertiajs/vue3';
import AppLayout from '@/layouts/AppLayout.vue';
import Heading from '@/components/Heading.vue';
import { Button } from '@/components/ui/button';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';

defineProps({
    projects: Array,
});
</script>

<template>
    <AppLayout>
        <div class="p-6">
            <div class="flex justify-between items-center mb-6">
                <Heading title="My Projects" description="Here is a list of your projects." />
                <Button as-child>
                    <Link :href="route('projects.create')">
                    Create Project
                    </Link>
                </Button>
            </div>
            <Card>
                <CardHeader>
                    <CardTitle>All Projects</CardTitle>
                </CardHeader>
                <CardContent>
                    <ul class="space-y-4">
                        <li v-for="project in projects" :key="project.id" class="flex justify-between items-center">
                            <span>{{ project.name }}</span>
                            <Button variant="outline" size="sm" as-child>
                                <Link :href="route('projects.edit', project.id)">
                                    Edit
                                </Link>
                            </Button>
                        </li>
                    </ul>
                    <p v-if="!projects.length" class="text-muted-foreground">
                        You don't have any projects yet.
                    </p>
                </CardContent>
            </Card>
        </div>
    </AppLayout>
</template>
