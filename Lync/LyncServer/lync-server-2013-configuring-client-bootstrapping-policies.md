---
title: 'Lync Server 2013 : configuration des stratégies de démarrage client'
description: 'Lync Server 2013 : configuration des stratégies de démarrage client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545630"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="911a1-103">Configuration des stratégies de démarrage client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="911a1-103">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="911a1-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="911a1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="911a1-105">La console de gestion des stratégies de groupe et l’éditeur d’objets de stratégie de groupe sont des outils qui vous permettent de gérer la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="911a1-105">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="911a1-106">Les modèles d’administration de la stratégie de groupe Office sont Lync 2013. admx (ADMX) et. adml (ADML), qui contiennent les paramètres de stratégie basés sur le registre que vous configurez pour les objets de stratégie de groupe dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="911a1-106">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="911a1-107">Les fichiers ADML sont des compléments spécifiques à la langue pour les fichiers ADMX.</span><span class="sxs-lookup"><span data-stu-id="911a1-107">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="911a1-108">Chaque fichier ADMX et ADML contient les paramètres de stratégie pour une seule application Office.</span><span class="sxs-lookup"><span data-stu-id="911a1-108">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="911a1-109">Pour plus d’informations, reportez-vous à la rubrique « Office 2013 administrative Template Files (ADMX, ADML) » dans la documentation Office 2013 à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="911a1-109">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="911a1-110">Pour Lync 2013, plusieurs stratégies de démarrage client doivent être configurées avant que les utilisateurs se connectent au serveur pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="911a1-110">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="911a1-111">Par exemple, les serveurs et le mode de sécurité par défaut que le client doit utiliser jusqu’à ce que la connexion soit terminée.</span><span class="sxs-lookup"><span data-stu-id="911a1-111">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="911a1-112">Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans les registres des ordinateurs des utilisateurs avant qu’ils se connectent et commencent à recevoir des paramètres de mise en service intrabande à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="911a1-112">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="911a1-113">Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a1-113">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="911a1-114">Paramètres des stratégies de groupe de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="911a1-114">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="911a1-115">Paramètre de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="911a1-115">Group Policy setting</span></span></th>
<th><span data-ttu-id="911a1-116">Description</span><span class="sxs-lookup"><span data-stu-id="911a1-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="911a1-117">Spécifier le serveur</span><span class="sxs-lookup"><span data-stu-id="911a1-117">Specify Server</span></span><br />
<span data-ttu-id="911a1-118">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="911a1-118">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="911a1-119">Indique comment Lync 2013 identifie le transport et le serveur à utiliser lors de la connexion.</span><span class="sxs-lookup"><span data-stu-id="911a1-119">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="911a1-120">Dans ce paramètre, vous spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="911a1-120">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="911a1-121">ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisés par les clients et les contacts fédérés lors de la connexion en dehors du pare-feu externe.</span><span class="sxs-lookup"><span data-stu-id="911a1-121">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="911a1-122">ServerAddressInternal : spécifie le nom du serveur ou l’adresse IP utilisés lorsque les clients se connectent à l’intérieur du pare-feu de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="911a1-122">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="911a1-123">Transport : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="911a1-123">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-124">Versions de serveur supplémentaires prises en charge</span><span class="sxs-lookup"><span data-stu-id="911a1-124">Additional server versions supported</span></span><br />
<span data-ttu-id="911a1-125">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="911a1-125">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="911a1-126">Spécifie une liste de noms de versions de serveur séparés par des points-virgules sur lesquels Lync Server 2013 se connectera, en plus des versions de serveur prises en charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="911a1-126">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-127">Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="911a1-127">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="911a1-128">Télécharge automatiquement les journaux d’échec de connexion vers Lync Server pour analyse.</span><span class="sxs-lookup"><span data-stu-id="911a1-128">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="911a1-129">Aucun journal n’est chargé automatiquement si la connexion réussit.</span><span class="sxs-lookup"><span data-stu-id="911a1-129">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="911a1-130">Si cette stratégie n’est pas configurée, voici ce qui se produit :</span><span class="sxs-lookup"><span data-stu-id="911a1-130">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="911a1-131">Pour les utilisateurs Lync Online : les journaux d’échec de connexion sont téléchargés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="911a1-131">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="911a1-132">Pour les utilisateurs de Lync sur site : une boîte de dialogue de confirmation s’affiche avant le téléchargement.</span><span class="sxs-lookup"><span data-stu-id="911a1-132">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="911a1-133">Lorsque ce paramètre est désactivé, les journaux de connexion sont téléchargés automatiquement vers le serveur Lync pour les utilisateurs Lync Online et Lync Online.</span><span class="sxs-lookup"><span data-stu-id="911a1-133">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="911a1-134">Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="911a1-134">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-135">Désactiver le secours HTTP pour la connexion SIP</span><span class="sxs-lookup"><span data-stu-id="911a1-135">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="911a1-136">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="911a1-136">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="911a1-137">Empêche Lync Server d’essayer de se connecter au serveur à l’aide du protocole HTTP, si TLS ou TCP ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="911a1-137">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="911a1-138">Par défaut, Lync tente d’abord de se connecter au serveur à l’aide du protocole TLS ou TCP et, si aucune de ces méthodes de transport ne réussit, Lync tente de se connecter à l’aide du protocole HTTP.</span><span class="sxs-lookup"><span data-stu-id="911a1-138">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="911a1-139">Utilisez cette stratégie pour désactiver la tentative de remplacement de la connexion HTTP.</span><span class="sxs-lookup"><span data-stu-id="911a1-139">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-140">Exiger des informations d’identification d’ouverture de session</span><span class="sxs-lookup"><span data-stu-id="911a1-140">Require logon credentials</span></span><br />
<span data-ttu-id="911a1-141">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="911a1-141">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="911a1-142">Oblige l’utilisateur à fournir des informations d’identification d’ouverture de session pour Lync au lieu d’utiliser automatiquement les informations d’identification Windows lors de la connexion à un serveur SIP.</span><span class="sxs-lookup"><span data-stu-id="911a1-142">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-143">Désactiver la vérification de la version du serveur</span><span class="sxs-lookup"><span data-stu-id="911a1-143">Disable server version check</span></span><br />
<span data-ttu-id="911a1-144">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="911a1-144">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="911a1-145">Si vous définissez cette stratégie sur 1, empêche Lync de vérifier le nom et la version du serveur avant de se connecter.</span><span class="sxs-lookup"><span data-stu-id="911a1-145">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="911a1-146">Par défaut, Lync effectue ces contrôles avant de se connecter.</span><span class="sxs-lookup"><span data-stu-id="911a1-146">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-147">Activer l’utilisation de BITS pour télécharger les fichiers du service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="911a1-147">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="911a1-148">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="911a1-148">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="911a1-149">Permet à Lync d’utiliser le service de transfert intelligent en arrière-plan (BITS) pour télécharger les fichiers des services de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="911a1-149">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-150">Configurer le mode de sécurité SIP</span><span class="sxs-lookup"><span data-stu-id="911a1-150">Configure SIP security mode</span></span><br />
<span data-ttu-id="911a1-151">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="911a1-151">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="911a1-152">Permet à Lync d’envoyer et de recevoir des messages instantanés de manière plus sécurisée.</span><span class="sxs-lookup"><span data-stu-id="911a1-152">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="911a1-153">Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="911a1-153">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="911a1-154">Si vous ne configurez pas ce paramètre de stratégie, Lync peut utiliser n’importe quel transport.</span><span class="sxs-lookup"><span data-stu-id="911a1-154">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="911a1-155">Toutefois, s’il n’utilise pas le protocole TLS et que le serveur authentifie les utilisateurs, Lync doit utiliser l’authentification NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="911a1-155">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-156">Délai initial de téléchargement du carnet d’adresses global</span><span class="sxs-lookup"><span data-stu-id="911a1-156">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="911a1-157">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="911a1-157">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="911a1-158">Spécifie le délai d’attente avant le téléchargement de la liste d’adresses globale.</span><span class="sxs-lookup"><span data-stu-id="911a1-158">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="911a1-159">La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.</span><span class="sxs-lookup"><span data-stu-id="911a1-159">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-160">Empêcher les utilisateurs d’exécuter Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="911a1-160">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="911a1-161">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="911a1-161">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="911a1-162">Empêche les utilisateurs d’exécuter Lync.</span><span class="sxs-lookup"><span data-stu-id="911a1-162">Prevents users from running Lync.</span></span> <span data-ttu-id="911a1-163">Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="911a1-163">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-164">Autoriser le stockage des mots de passe utilisateur</span><span class="sxs-lookup"><span data-stu-id="911a1-164">Allow storage of user passwords</span></span><br />
<span data-ttu-id="911a1-165">SavePassword</span><span class="sxs-lookup"><span data-stu-id="911a1-165">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="911a1-166">Permet à Lync de stocker des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="911a1-166">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-167">Configurer le mode de compression SIP</span><span class="sxs-lookup"><span data-stu-id="911a1-167">Configure SIP compression mode</span></span><br />
<span data-ttu-id="911a1-168">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="911a1-168">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="911a1-p112">Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.</span><span class="sxs-lookup"><span data-stu-id="911a1-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-172">Liste de domaines approuvés</span><span class="sxs-lookup"><span data-stu-id="911a1-172">Trusted Domain List</span></span><br />
<span data-ttu-id="911a1-173">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="911a1-173">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="911a1-174">Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.</span><span class="sxs-lookup"><span data-stu-id="911a1-174">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="911a1-p113">Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau suivant indique l’ordre de priorité qui est appliqué aux paramètres lorsqu’un conflit se produit.</span><span class="sxs-lookup"><span data-stu-id="911a1-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="911a1-177">Priorité des stratégies de groupe</span><span class="sxs-lookup"><span data-stu-id="911a1-177">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="911a1-178">Precedence</span><span class="sxs-lookup"><span data-stu-id="911a1-178">Precedence</span></span></th>
<th><span data-ttu-id="911a1-179">Emplacement ou méthode de définition</span><span class="sxs-lookup"><span data-stu-id="911a1-179">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="911a1-180">0,1</span><span class="sxs-lookup"><span data-stu-id="911a1-180">1</span></span></p></td>
<td><p><span data-ttu-id="911a1-181">Mise en service intrabande Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="911a1-181">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-182">n°2</span><span class="sxs-lookup"><span data-stu-id="911a1-182">2</span></span></p></td>
<td><p><span data-ttu-id="911a1-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="911a1-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a1-184">3</span><span class="sxs-lookup"><span data-stu-id="911a1-184">3</span></span></p></td>
<td><p><span data-ttu-id="911a1-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="911a1-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a1-186">4 </span><span class="sxs-lookup"><span data-stu-id="911a1-186">4</span></span></p></td>
<td><p><span data-ttu-id="911a1-187">La boîte de dialogue Lync-options dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="911a1-187">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="911a1-188">Pour définir des paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration Lync 2013</span><span class="sxs-lookup"><span data-stu-id="911a1-188">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="911a1-189">Créez un dossier racine pour contenir tous les fichiers ADMX indépendants de la langue.</span><span class="sxs-lookup"><span data-stu-id="911a1-189">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="911a1-190">Par exemple, créez le dossier de racine pour le magasin central sur votre contrôleur de domaine à cet emplacement :</span><span class="sxs-lookup"><span data-stu-id="911a1-190">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="911a1-191">Cette procédure suppose que vous souhaitez gérer plusieurs ordinateurs de votre domaine.</span><span class="sxs-lookup"><span data-stu-id="911a1-191">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="911a1-192">Dans ce cas, vous stockez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal.</span><span class="sxs-lookup"><span data-stu-id="911a1-192">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="911a1-193">Ceci fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine.</span><span class="sxs-lookup"><span data-stu-id="911a1-193">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="911a1-194">Créez un sous-dossier pour chaque langue que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="911a1-194">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="911a1-195">Ces sous-dossiers contiennent les fichiers de ressources ADML propres à une langue.</span><span class="sxs-lookup"><span data-stu-id="911a1-195">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="911a1-196">Par exemple, créez un sous-dossier pour l’anglais des États-Unis (en-US) à cet emplacement :</span><span class="sxs-lookup"><span data-stu-id="911a1-196">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

