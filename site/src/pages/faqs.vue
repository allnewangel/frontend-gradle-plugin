<template>
    <section>
        <fgp-main-title>Frequently asked questions</fgp-main-title>

        <nav>
            <ul>
                <li>
                    <fgp-site-link path="#node-npm-npx-direct-use">
                        How to use <fgp-code>node</fgp-code>/<fgp-code>npm</fgp-code>/<fgp-code>npx</fgp-code>
                        executables apart from Gradle when the Node.js distribution is downloaded by the plugin?
                    </fgp-site-link>
                </li>
                <li>
                    <fgp-site-link path="#yarn-direct-use">
                        How to use <fgp-code>yarn</fgp-code> executable apart from Gradle when the Yarn distribution is
                        downloaded by the plugin?
                    </fgp-site-link>
                </li>
                <li>
                    <fgp-site-link path="#unsupported-platform-exception">
                        What should I do when error <fgp-code>UnsupportedPlatformException</fgp-code> occurs?
                    </fgp-site-link>
                </li>
            </ul>
        </nav>

        <fgp-node-npm-npx-direct-use-faq id="node-npm-npx-direct-use" />
        <fgp-yarn-direct-use-faq id="yarn-direct-use" />
        <fgp-unsupported-platform-exception-faq id="unsupported-platform-exception" />
    </section>
</template>

<script>
import Vue from "vue";
import fgpCode from "../components/code";
import fgpMainTitle from "../components/main-title";
import fgpNodeNpmNpxDirectUseFaq from "../components/faq/node-npm-npx-direct-use-faq";
import fgpPageMeta from "../mixin/page-meta";
import fgpSiteLink from "../components/link/site-link";
import fgpUnsupportedPlatformExceptionFaq from "../components/faq/unsupported-platform-exception-faq";
import fgpYarnDirectUseFaq from "../components/faq/yarn-direct-use-faq";

export default Vue.component("fgp-faqs", {
    components: {
        fgpCode,
        fgpMainTitle,
        fgpNodeNpmNpxDirectUseFaq,
        fgpSiteLink,
        fgpUnsupportedPlatformExceptionFaq,
        fgpYarnDirectUseFaq
    },
    mixins: [fgpPageMeta],
    data() {
        return {
            htmlTitle: "Frequently asked questions",
            metaDescription: "Using node, npm, npx, yarn executables apart from Gradle and resolving common issues.",
            linkCanonicalHref: process.env.FGP_WEBSITE_URL + 'faqs/'
        }
    }
});
</script>
