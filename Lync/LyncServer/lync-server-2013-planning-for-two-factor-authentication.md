---
title: 'Lync Server 2013 : planification de l’authentification à deux facteurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1932164cd1236257bbb81d1503b0310c8c55526e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513451"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="32823-102">Planification de l’authentification à deux facteurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32823-102">Planning for two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32823-103">_**Dernière modification de la rubrique :** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="32823-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="32823-104">Voici une liste de considérations relatives au déploiement lors de la configuration d’un environnement Microsoft Lync Server 2013 afin de prendre en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="32823-105">Prise en charge des clients</span><span class="sxs-lookup"><span data-stu-id="32823-105">Client Support</span></span>

<span data-ttu-id="32823-106">Les mises à jour cumulatives de Lync 2013 pour Lync Server 2013 : client de bureau de juillet 2013 et tous les clients mobiles prennent actuellement en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="32823-107">Conditions requises pour la topologie</span><span class="sxs-lookup"><span data-stu-id="32823-107">Topology Requirements</span></span>

<span data-ttu-id="32823-108">Les clients sont vivement encouragés à déployer l’authentification à deux facteurs à l’aide de Lync Server 2013 dédié avec des mises à jour cumulatives pour Lync Server 2013 : juillet 2013 Edge, directeur et pools d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="32823-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="32823-109">Pour activer l’authentification passive pour les utilisateurs de Lync, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="32823-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32823-110">Type de configuration</span><span class="sxs-lookup"><span data-stu-id="32823-110">Configuration Type</span></span></th>
<th><span data-ttu-id="32823-111">Type de service</span><span class="sxs-lookup"><span data-stu-id="32823-111">Service Type</span></span></th>
<th><span data-ttu-id="32823-112">Server Role</span><span class="sxs-lookup"><span data-stu-id="32823-112">Server Role</span></span></th>
<th><span data-ttu-id="32823-113">Type d’authentification à désactiver</span><span class="sxs-lookup"><span data-stu-id="32823-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32823-114">Service Web</span><span class="sxs-lookup"><span data-stu-id="32823-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="32823-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="32823-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="32823-116">Directeur</span><span class="sxs-lookup"><span data-stu-id="32823-116">Director</span></span></p></td>
<td><p><span data-ttu-id="32823-117">Kerberos, NTLM et certificat</span><span class="sxs-lookup"><span data-stu-id="32823-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32823-118">Service Web</span><span class="sxs-lookup"><span data-stu-id="32823-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="32823-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="32823-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="32823-120">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="32823-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="32823-121">Kerberos, NTLM et certificat</span><span class="sxs-lookup"><span data-stu-id="32823-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32823-122">Établir</span><span class="sxs-lookup"><span data-stu-id="32823-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="32823-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="32823-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="32823-124">Edge</span><span class="sxs-lookup"><span data-stu-id="32823-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="32823-125">Kerberos et NTLM</span><span class="sxs-lookup"><span data-stu-id="32823-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32823-126">Établir</span><span class="sxs-lookup"><span data-stu-id="32823-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="32823-127">Inscriptions</span><span class="sxs-lookup"><span data-stu-id="32823-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="32823-128">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="32823-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="32823-129">Kerberos et NTLM</span><span class="sxs-lookup"><span data-stu-id="32823-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32823-130">À moins que ces types d’authentification soient désactivés au niveau du service, toutes les autres versions du client Lync ne pourront pas se connecter une fois que l’authentification à deux facteurs est activée dans dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="32823-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="32823-131">Découverte de service Lync</span><span class="sxs-lookup"><span data-stu-id="32823-131">Lync Service Discovery</span></span>

<span data-ttu-id="32823-132">Les enregistrements DNS utilisés par les clients internes et/ou externes pour découvrir Lync services doivent être configurés pour être résolus en Lync Server qui n’est pas activé pour l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="32823-133">Avec cette configuration, les utilisateurs des pools Lync qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas tenus d’entrer un code confidentiel à authentifier, tandis que les utilisateurs des pools Lync qui sont activés pour l’authentification à deux facteurs doivent entrer leur code confidentiel pour s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="32823-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="32823-134">Authentification Exchange</span><span class="sxs-lookup"><span data-stu-id="32823-134">Exchange Authentication</span></span>

<span data-ttu-id="32823-135">Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent constater que certaines fonctionnalités du client Lync ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="32823-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="32823-136">Cette fonctionnalité est actuellement conçue par défaut, car le client Lync ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="32823-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="32823-137">Contacts Lync</span><span class="sxs-lookup"><span data-stu-id="32823-137">Lync Contacts</span></span>

<span data-ttu-id="32823-138">Les utilisateurs de Lync configurés pour tirer parti de la fonctionnalité de magasin de contacts unifié constateront que leurs contacts ne sont plus disponibles après la connexion à l’aide de l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="32823-139">Vous devez utiliser l’applet de commande **Invoke-CsUcsRollback** pour supprimer les contacts utilisateur existants du magasin de contacts unifié et les stocker dans Lync Server 2013 avant d’activer l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="32823-140">Recherche de compétences</span><span class="sxs-lookup"><span data-stu-id="32823-140">Skill Search</span></span>

<span data-ttu-id="32823-141">Les clients qui ont configuré la fonctionnalité de recherche de compétences dans leur environnement Lync constateront que cette fonctionnalité ne fonctionne pas lorsque Lync est activé pour l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="32823-142">C’est par conception, car Microsoft SharePoint ne prend actuellement pas en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="32823-143">Informations d’identification Lync</span><span class="sxs-lookup"><span data-stu-id="32823-143">Lync Credentials</span></span>

<span data-ttu-id="32823-144">Il existe un certain nombre de considérations relatives au déploiement impliquant des informations d’identification Lync enregistrées susceptibles d’avoir un impact sur les utilisateurs configurés pour utiliser l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="32823-145">Suppression des informations d’identification enregistrées</span><span class="sxs-lookup"><span data-stu-id="32823-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="32823-146">Les utilisateurs des clients de bureau doivent utiliser l’option de **Suppression de mes informations de connexion** dans le client Lync et supprimer leur dossier de profil SIP de% LocalAppData% \\ Microsoft \\ Office \\ 15,0 \\ Lync avant de tenter de signer pour la première fois à l’aide de l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="32823-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="32823-147">DisableNTCredentials</span></span>

<span data-ttu-id="32823-148">Avec la méthode d’authentification Kerberos ou NTLM, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="32823-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="32823-149">Dans un déploiement standard de Lync Server 2013 où Kerberos et/ou NTLM sont activés pour l’authentification, les utilisateurs ne doivent pas nécessairement entrer leurs informations d’identification chaque fois qu’ils se connectent.</span><span class="sxs-lookup"><span data-stu-id="32823-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="32823-150">Si les utilisateurs sont involontairement invités à fournir des informations d’identification avant qu’ils ne soient invités à entrer leur code confidentiel, la clé de Registre **DisableNTCredentials** peut être involontairement configurée sur des ordinateurs clients, éventuellement par le biais de la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="32823-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="32823-151">Pour empêcher l’invite supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :</span><span class="sxs-lookup"><span data-stu-id="32823-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="32823-152">HKEY \_ \_ stratégies logicielles de l’ordinateur local \\ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="32823-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="32823-153">REG \_ DWORD : DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="32823-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="32823-154">Valeur : 0x0</span><span class="sxs-lookup"><span data-stu-id="32823-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="32823-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="32823-155">SavePassword</span></span>

<span data-ttu-id="32823-156">Lorsqu’un utilisateur se connecte à Lync pour la première fois, il est invité à enregistrer son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="32823-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="32823-157">Si cette option est sélectionnée, le certificat client de l’utilisateur est stocké dans le magasin de certificats personnel et les informations d’identification Windows de l’utilisateur sont stockées dans le gestionnaire d’informations d’identification de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="32823-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="32823-158">Le paramètre de Registre **SavePassword** doit être désactivé lorsque Lync est configuré pour prendre en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="32823-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="32823-159">Pour empêcher les utilisateurs d’enregistrer leurs mots de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :</span><span class="sxs-lookup"><span data-stu-id="32823-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="32823-160">HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="32823-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="32823-161">REG \_ DWORD : SavePassword</span><span class="sxs-lookup"><span data-stu-id="32823-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="32823-162">Valeur : 0x0</span><span class="sxs-lookup"><span data-stu-id="32823-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="32823-163">Relecture des jetons AD FS 2,0</span><span class="sxs-lookup"><span data-stu-id="32823-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="32823-164">AD FS 2,0 fournit une fonctionnalité appelée détection de relecture de jeton, grâce à laquelle plusieurs demandes de jeton utilisant le même jeton peuvent être détectées, puis rejetées.</span><span class="sxs-lookup"><span data-stu-id="32823-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="32823-165">Lorsque cette fonctionnalité est activée, la détection de relecture de jeton protège l’intégrité des demandes d’authentification dans WS-Federation le profil WebSSO passif et le profil SAML en s’assurant que le même jeton n’est jamais utilisé plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="32823-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="32823-166">Cette fonctionnalité doit être activée dans les situations où la sécurité est une préoccupation majeure, par exemple lors de l’utilisation de kiosques.</span><span class="sxs-lookup"><span data-stu-id="32823-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="32823-167">Pour plus d’informations sur la détection de relecture de jetons, voir Best Practices for Secure Planning and Deployment of AD FS 2,0 à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) .</span><span class="sxs-lookup"><span data-stu-id="32823-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="32823-168">Accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="32823-168">External User Access</span></span>

<span data-ttu-id="32823-169">La configuration d’un proxy AD FS ou d’un proxy inverse pour prendre en charge l’authentification à deux facteurs de Lync à partir de réseaux externes n’est pas abordée dans ces rubriques.</span><span class="sxs-lookup"><span data-stu-id="32823-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

