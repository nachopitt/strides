<script setup>
import { useForm } from '@inertiajs/vue3';
import AppLayout from '@/layouts/AppLayout.vue';
import Heading from '@/components/Heading.vue';
import { Button } from '@/components/ui/button';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { Input } from '@/components/ui/input';
import { Label } from '@/components/ui/label';

const props = defineProps({
    project: Object,
});

const form = useForm({
    name: props.project.name,
    description: props.project.description,
});

const submit = () => {
    form.put(route('projects.update', props.project.id));
};
</script>

<template>
    <AppLayout>
        <div class="p-6">
            <Heading title="Edit Project" :description="`Editing: ${project.name}`" />
            <Card class="max-w-2xl mx-auto">
                <CardHeader>
                    <CardTitle>Project Details</CardTitle>
                </CardHeader>
                <CardContent>
                    <form @submit.prevent="submit">
                        <div class="grid gap-6">
                            <div class="grid gap-2">
                                <Label for="name">Project Name</Label>
                                <Input id="name" v-model="form.name" type="text" required />
                            </div>
                            <div class="grid gap-2">
                                <Label for="description">Description</Label>
                                <Input id="description" v-model="form.description" type="text" />
                            </div>
                            <div class="flex justify-end">
                                <Button type="submit" :disabled="form.processing">
                                    Update Project
                                </Button>
                            </div>
                        </div>
                    </form>
                </CardContent>
            </Card>
        </div>
    </AppLayout>
</template>
