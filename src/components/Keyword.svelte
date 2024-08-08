<script>
    import { ReactSolid } from 'flowbite-svelte-icons';
    import ServerlessIcon from '$lib/icons/Serverless_Icon.svelte';
    import TypeScriptIcon from '$lib/icons/TypeScript_Icon.svelte';
    import AwsIcon from '$lib/icons/Aws_Icon.svelte';
    import NodeIcon from '$lib/icons/Node_Icon.svelte';
    import AwsLambdaIcon from '$lib/icons/Aws_Lambda_Icon.svelte';
    import TerraformIcon from '$lib/icons/Terraform_Icon.svelte';
    import AspIcon from '$lib/icons/Asp_Icon.svelte';
    import AgileIcon from '$lib/icons/Agile_Icon.svelte';
    export let description = "Skill/Tool";
    export let icon = "react";

    const iconMap = {
        react: ReactSolid,
        serverless: ServerlessIcon,
        typescript: TypeScriptIcon,
        aws: AwsIcon,
        node: NodeIcon,
        terraform: TerraformIcon,
        lambda: AwsLambdaIcon,
        asp: AspIcon,
        agile: AgileIcon
    }

    // @ts-ignore
    const SelectedIcon = iconMap[icon];
</script>

<div class="keyword-container">
    <div class="keyword-icon">
    {#if SelectedIcon}
        <svelte:component this={SelectedIcon} />
    {/if}
    </div>
    <div class="keyword-text">
        <div class="mb-4 text-base font-customMono">
        <span class="font-bold"> {description}</span>
        </div>
    </div>
</div>

<style>
    .keyword-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        border-radius: 10px;
        border-style: solid;
        border-width: 1px;
        margin: 5px;
        padding-right: 10px;
        background-color: white;
    }

    .keyword-icon {
        flex: 1;
        padding-left: 10px;
        padding-right: 10px;
    }

    .keyword-text {
        font-size: 1em;
        font-weight: bold;
        align-self: center;
        padding-top: 10px;
        color: black;
    }
</style>