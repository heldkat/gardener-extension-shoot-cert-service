<p>Packages:</p>
<ul>
<li>
<a href="#shoot-cert-service.extensions.config.gardener.cloud%2fv1alpha1">shoot-cert-service.extensions.config.gardener.cloud/v1alpha1</a>
</li>
</ul>
<h2 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1">shoot-cert-service.extensions.config.gardener.cloud/v1alpha1</h2>
<p>
<p>Package v1alpha1 contains the Certificate Shoot Service extension configuration.</p>
</p>
Resource Types:
<ul><li>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration</a>
</li></ul>
<h3 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration
</h3>
<p>
<p>Configuration contains information about the certificate service configuration.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code></br>
string</td>
<td>
<code>
shoot-cert-service.extensions.config.gardener.cloud/v1alpha1
</code>
</td>
</tr>
<tr>
<td>
<code>kind</code></br>
string
</td>
<td><code>Configuration</code></td>
</tr>
<tr>
<td>
<code>issuerName</code></br>
<em>
string
</em>
</td>
<td>
<p>IssuerName is the name of the issuer.</p>
</td>
</tr>
<tr>
<td>
<code>restrictIssuer</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>RestrictIssuer restricts the ACME issuer to shoot related domains.</p>
</td>
</tr>
<tr>
<td>
<code>defaultRequestsPerDayQuota</code></br>
<em>
int32
</em>
</td>
<td>
<em>(Optional)</em>
<p>DefaultRequestsPerDayQuota restricts the certificate requests per issuer (can be overriden in issuer spec)</p>
</td>
</tr>
<tr>
<td>
<code>shootIssuers</code></br>
<em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.ShootIssuers">
ShootIssuers
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ShootIssuers contains enablement for issuers on shoot cluster</p>
</td>
</tr>
<tr>
<td>
<code>acme</code></br>
<em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.ACME">
ACME
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ACME contains the ACME default issuer related configuration. Either ACME or CA must be set.</p>
</td>
</tr>
<tr>
<td>
<code>ca</code></br>
<em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.CA">
CA
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>CA contains the CA default issuer related configuration. Either ACME or CA must be set.</p>
</td>
</tr>
<tr>
<td>
<code>healthCheckConfig</code></br>
<em>
github.com/gardener/gardener/extensions/pkg/apis/config/v1alpha1.HealthCheckConfig
</em>
</td>
<td>
<em>(Optional)</em>
<p>HealthCheckConfig is the config for the health check controller.</p>
</td>
</tr>
<tr>
<td>
<code>privateKeyDefaults</code></br>
<em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.PrivateKeyDefaults">
PrivateKeyDefaults
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>PrivateKeyDefaults default algorithm and sizes for certificate private keys.</p>
</td>
</tr>
<tr>
<td>
<code>inClusterACMEServerNamespaceMatchLabel</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>InClusterACMEServerNamespaceMatchLabel is the match label used to create a network policy to allow egress from the &ldquo;cert-controller-manager&rdquo; to a namespace with these labels.
It can be set to allow access to an in-cluster ACME server from the cert-controller-manager.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.ACME">ACME
</h3>
<p>
(<em>Appears on:</em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration</a>)
</p>
<p>
<p>ACME holds information about the ACME issuer used for the certificate service.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>email</code></br>
<em>
string
</em>
</td>
<td>
<p>Email is the e-mail address used for the ACME issuer.</p>
</td>
</tr>
<tr>
<td>
<code>server</code></br>
<em>
string
</em>
</td>
<td>
<p>Server is the server address used for the ACME issuer.</p>
</td>
</tr>
<tr>
<td>
<code>privateKey</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>PrivateKey is the key used for the ACME issuer.</p>
</td>
</tr>
<tr>
<td>
<code>propagationTimeout</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.32/#duration-v1-meta">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>PropagationTimeout is the timeout for DNS01 challenges.</p>
</td>
</tr>
<tr>
<td>
<code>precheckNameservers</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>PrecheckNameservers is used to specify a comma-separated list of DNS servers for checking availability for DNS
challenge before calling ACME CA</p>
</td>
</tr>
<tr>
<td>
<code>caCertificates</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>CACertificates are custom root certificates to be made available for the cert-controller-manager</p>
</td>
</tr>
<tr>
<td>
<code>deactivateAuthorizations</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DeactivateAuthorizations enables deactivation of authorizations after successful certificate request</p>
</td>
</tr>
<tr>
<td>
<code>skipDNSChallengeValidation</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>SkipDNSChallengeValidation skips the DNS challenge validation</p>
</td>
</tr>
</tbody>
</table>
<h3 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.CA">CA
</h3>
<p>
(<em>Appears on:</em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration</a>)
</p>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>certificate</code></br>
<em>
string
</em>
</td>
<td>
<p>Certificate is the public certificate of the CA in PEM format.</p>
</td>
</tr>
<tr>
<td>
<code>certificateKey</code></br>
<em>
string
</em>
</td>
<td>
<p>CertificateKey is the private certificate key of the CA in PEM format.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.PrivateKeyDefaults">PrivateKeyDefaults
</h3>
<p>
(<em>Appears on:</em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration</a>)
</p>
<p>
<p>PrivateKeyDefaults default algorithm and sizes for certificate private keys.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>algorithm</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Algorithm is the default algorithm (&lsquo;RSA&rsquo; or &lsquo;ECDSA&rsquo;)</p>
</td>
</tr>
<tr>
<td>
<code>sizeRSA</code></br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>SizeRSA is the default size for RSA algorithm.</p>
</td>
</tr>
<tr>
<td>
<code>sizeECDSA</code></br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>SizeECDSA is the default size for ECDSA algorithm.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.ShootIssuers">ShootIssuers
</h3>
<p>
(<em>Appears on:</em>
<a href="#shoot-cert-service.extensions.config.gardener.cloud/v1alpha1.Configuration">Configuration</a>)
</p>
<p>
<p>ShootIssuers holds enablement for issuers on shoot cluster</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>enabled</code></br>
<em>
bool
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<hr/>
<p><em>
Generated with <a href="https://github.com/ahmetb/gen-crd-api-reference-docs">gen-crd-api-reference-docs</a>
</em></p>
