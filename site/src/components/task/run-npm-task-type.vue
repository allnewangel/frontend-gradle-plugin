<template>
    <fgp-task name="RunNpm" :type="true">
        <template v-slot:title
            >Run a custom command with <fgp-code>npm</fgp-code></template
        >
        <template v-slot:description>
            <p>
                The plugin provides the task type
                <fgp-code>org.siouan.frontendgradleplugin.infrastructure.gradle.RunNpm</fgp-code> that allows
                creating a custom task to run a frontend script. The <fgp-code>script</fgp-code> property must be set
                with the corresponding command. Then, choose the appropriate task dependency: make the task either
                depends on <fgp-task-link name="installNode" /> task or on <fgp-task-link name="installFrontend" />
                task. The code hereafter shows the configuration required to run a linter:
            </p>

            <fgp-gradle-scripts id="run-npm-example" class="my-3">
                <template v-slot:groovy>
                    <pre><fgp-code>import org.siouan.frontendgradleplugin.infrastructure.gradle.RunNpm
tasks.register('e2e', RunNpm) {
    <fgp-code-comment>// dependsOn tasks.named('installNode')
    // dependsOn tasks.named('installFrontend')</fgp-code-comment>
    script = 'run lint'
}</fgp-code></pre>
                </template>
                <template v-slot:kotlin>
                    <pre><fgp-code>import org.siouan.frontendgradleplugin.infrastructure.gradle.RunNpm
tasks.register&lt;RunNpm&gt;("e2e") {
    <fgp-code-comment>// dependsOn(tasks.named("installNode"))
    // dependsOn(tasks.named("installFrontend"))</fgp-code-comment>
    script.set("run lint")
}</fgp-code></pre>
                </template>
            </fgp-gradle-scripts>
        </template>
    </fgp-task>
</template>

<script>
import Vue from "vue";
import fgpCode from "../code";
import fgpGradleScripts from "../gradle-scripts";
import fgpTask from "./task";
import fgpTaskLink from "../link/task-link";

export default Vue.component("fgp-run-npm-task-type", {
    components: {
        fgpCode,
        fgpGradleScripts,
        fgpTask,
        fgpTaskLink
    }
});
</script>
