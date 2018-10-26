---
title: Configuration des stratégies d’amorçage clientes dans Lync Server 2013
TOCTitle: Configuration des stratégies d’amorçage clientes dans Lync Server 2013
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425941(v=OCS.15)
ms:contentKeyID: 49297065
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies d’amorçage clientes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La Console de gestion des stratégies de groupe (GPMC) et l’Éditeur d’objets de stratégie de groupe sont des outils que vous utilisez pour gérer la stratégie de groupe. Le modèle d’administration de stratégie de groupe Office est accompagné des modèles d’administration .admx (ADMX) et .adml (ADML) de Lync 2013, qui contiennent les paramètres de stratégie basés sur le Registre que vous configurez pour les objets de stratégie de groupe du domaine. Les fichiers ADML sont des compléments spécifiques à une langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie d’une seule application Office.

Pour Lync 2013, il existe plusieurs stratégies de démarrage clientes que vous devriez configurer avant que les utilisateurs ne se connectent au serveur pour la première fois. C’est le cas par exemple des serveurs par défaut et du mode de sécurité que le client doit utiliser jusqu’à ce que l’authentification soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans le Registre des ordinateurs des utilisateurs avant qu’ils ne se connectent et commencent à recevoir des paramètres de mise en service intrabande en provenance du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Lync 2013.

### Paramètres de stratégie de groupe pour Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre de stratégie de groupe</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Spécifier le serveur<br />
(ConfigurationMode)</p></td>
<td><p>Spécifie la façon dont Lync 2013 identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, spécifiez ce qui suit :</p><ul><li><p>ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisé par les clients et les contacts fédérés lors de la connexion depuis l’extérieur du pare-feu externe.</p></li><li><p>ServerAddressInternal : spécifie le nom ou l’adresse IP du serveur utilisé quand les clients se connectent depuis l’intérieur du pare-feu de l’organisation.</p></li><li><p>Transport : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security).</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Versions de serveur supplémentaires prises en charge<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Spécifie la liste des noms des versions de serveurs, séparés par des points-virgules, auxquels Lync Server 2013 se connectera, ainsi que les versions de serveurs prises en charge par défaut.</p></td>
</tr>
<tr class="odd">
<td><p>Désactiver le téléchargement automatique des journaux d’échecs de connexion (DisableAutomaticSendTracing)</p></td>
<td><p>Télécharge automatiquement les journaux d’échecs de connexion vers Lync Server à des fins d’analyse. Aucun journal n’est téléchargé automatiquement si l’authentification réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :</p>
<dl>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs Lync Online : les journaux d’échecs de connexion sont téléchargés automatiquement.</p>
</dd>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs locaux Lync : une boîte de dialogue de confirmation s’affiche à l’intention de l’utilisateur avant le téléchargement.</p>
</dd>
</dl>
<p>Quand ce paramètre est désactivé, les journaux de connexion sont automatiquement téléchargés vers le serveur Lync Server pour les utilisateurs locaux Lync et les utilisateurs Lync Online. Quand ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.</p></td>
</tr>
<tr class="even">
<td><p>Désactiver le remplacement HTTP de la connexion SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Empêche Lync Server d’essayer de se connecter au serveur via le protocole HTTP, si les protocoles TLS ou TCP ne sont pas disponibles. Par défaut, Lync tente d’abord de se connecter au serveur à l’aide des protocoles TLS ou TCP. Si aucun de ces modes de transport n’est disponible, Lync essaie de se connecter à l’aide du protocole HTTP. Utilisez cette stratégie pour désactiver la tentative de remplacement de la connexion HTTP.</p></td>
</tr>
<tr class="odd">
<td><p>Exiger des informations d’identification<br />
(DisableNTCredentials)</p></td>
<td><p>Oblige l’utilisateur à fournir des informations d’identification d’ouverture de session pour Lync au lieu d’utiliser automatiquement les données d’identification Windows quand il se connecte à un serveur SIP.</p></td>
</tr>
<tr class="even">
<td><p>Désactiver la vérification de version du serveur<br />
(DisableServerCheck)</p></td>
<td><p>Si vous affectez la valeur 1 à cette stratégie, Lync ne peut pas vérifier le nom et la version du serveur avant la connexion. Par défaut, Lync effectue ces vérifications avant la connexion.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser l’utilisation de BITS pour télécharger les fichiers du service de carnet d’adresses<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permet à Lync d’utiliser le service BITS (Background Intelligent Transfer Service) pour télécharger les fichiers des services de carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de sécurité SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permet à Lync d’envoyer et de recevoir les messages instantanés de façon plus sécurisée. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.</p>
<p>Si vous ne configurez pas ce paramètre de stratégie, Lync ne peut utiliser aucun transport. Mais s’il n’utilise pas le protocole TLS et si le serveur authentifie les utilisateurs, Lync doit utiliser l’authentification NTLM ou Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Délai initial de téléchargement du carnet d’adresses global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Spécifie le délai d’attente avant le téléchargement de la liste d’adresses globale. La valeur par défaut est 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de la liste d’adresses globale durant une période aléatoire comprise entre 0 et 60 minutes.</p></td>
</tr>
<tr class="even">
<td><p>Empêcher les utilisateurs d’exécuter Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Bloque l’utilisation de Lync. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser le stockage des mots de passe utilisateur<br />
(SavePassword)</p></td>
<td><p>Permet à Lync de conserver les mots de passe.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de compression SIP<br />
(SipCompression)</p></td>
<td><p>Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.</p></td>
</tr>
<tr class="odd">
<td><p>Liste de domaines approuvés<br />
(TrustModelData)</p></td>
<td><p>Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.</p></td>
</tr>
</tbody>
</table>


Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau suivant indique l’ordre de priorité qui est appliqué aux paramètres lorsqu’un conflit se produit.

### Priorité des stratégies de groupe

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Priorité</th>
<th>Emplacement ou méthode de définition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Mise en service intrabande de Lync Server 2013</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Boîte de dialogue Lync - Options dans Lync 2013</p></td>
</tr>
</tbody>
</table>


## Pour définir des paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration de Lync 2013

1.  Créez un dossier de niveau racine destiné à contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier racine du magasin central sur votre contrôleur de domaine à cet emplacement :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]  
    > Pour cette procédure, nous supposons que vous voulez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, stockez les modèles dans un magasin central au sein du dossier Sysvol sur le contrôleur de domaine principal. Ceci fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine.

2.  Créez un sous-dossier pour chaque langue à utiliser. Ces sous-dossiers contiennent les fichiers de ressources ADML spécifiques à une langue. Par exemple, créez un sous-dossier pour l’anglais américain (EN-US) à l’emplacement suivant :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

Pour plus d’informations sur les fichiers ADMX, voir le Guide étape par étape de la gestion des fichiers ADMX de stratégie de groupe à l’adresse suivante : [http://go.microsoft.com/fwlink/?linkid=75124\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=75124%26clcid=0x40c).

