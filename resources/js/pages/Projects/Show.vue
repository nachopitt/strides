<script setup>
import AppLayout from '@/layouts/AppLayout.vue';
import Heading from '@/components/Heading.vue';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';

defineProps({
    project: Object,
});
</script>

<template>
    <AppLayout>
        <div class="p-6">
            <Heading title="Show Project" :description="`Showing: ${project.name}`" />
            <Card class="max-w-2xl mx-auto">
                <CardHeader>
                    <CardTitle>Project Details</CardTitle>
                </CardHeader>
                <CardContent>
                    <div class="space-y-4">
                        <div>
                            <h3 class="text-lg font-medium">Name</h3>
                            <p class="text-muted-foreground">{{ project.name }}</p>
                        </div>
                        <div>
                            <h3 class="text-lg font-medium">Description</h3>
                            <p class="text-muted-foreground">{{ project.description }}</p>
                        </div>
                    </div>
                </CardContent>
            </Card>
        </div>
    </AppLayout>
</template>
