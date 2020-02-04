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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="8b804-102">Planification de l’authentification à deux facteurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b804-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b804-103">_**Dernière modification de la rubrique :** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="8b804-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="8b804-104">La liste suivante répertorie les éléments à prendre en compte lors de la configuration d’un environnement Microsoft Lync Server 2013 pour prendre en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="8b804-105">Prise en charge des clients</span><span class="sxs-lookup"><span data-stu-id="8b804-105">Client Support</span></span>

<span data-ttu-id="8b804-106">Les mises à jour cumulatives de Lync 2013 pour Lync Server 2013 : le client de bureau 2013 de juillet et tous les clients mobiles prennent actuellement en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="8b804-107">Conditions requises pour la topologie</span><span class="sxs-lookup"><span data-stu-id="8b804-107">Topology Requirements</span></span>

<span data-ttu-id="8b804-108">Les clients sont fortement invités à déployer l’authentification à deux facteurs à l’aide de la 2013 dédiée de Lync Server avec des mises à jour cumulatives pour Lync Server 2013:2013 Edge, Director et groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="8b804-109">Pour activer l’authentification passive pour les utilisateurs de Lync, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b804-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b804-110">Type de configuration</span><span class="sxs-lookup"><span data-stu-id="8b804-110">Configuration Type</span></span></th>
<th><span data-ttu-id="8b804-111">Type de service</span><span class="sxs-lookup"><span data-stu-id="8b804-111">Service Type</span></span></th>
<th><span data-ttu-id="8b804-112">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="8b804-112">Server Role</span></span></th>
<th><span data-ttu-id="8b804-113">Type d’authentification à désactiver</span><span class="sxs-lookup"><span data-stu-id="8b804-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b804-114">Service web</span><span class="sxs-lookup"><span data-stu-id="8b804-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="8b804-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="8b804-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="8b804-116">Directeur</span><span class="sxs-lookup"><span data-stu-id="8b804-116">Director</span></span></p></td>
<td><p><span data-ttu-id="8b804-117">Kerberos, NTLM et par certificat</span><span class="sxs-lookup"><span data-stu-id="8b804-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b804-118">Service web</span><span class="sxs-lookup"><span data-stu-id="8b804-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="8b804-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="8b804-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="8b804-120">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="8b804-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="8b804-121">Kerberos, NTLM et par certificat</span><span class="sxs-lookup"><span data-stu-id="8b804-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b804-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="8b804-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="8b804-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="8b804-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="8b804-124">Edge</span><span class="sxs-lookup"><span data-stu-id="8b804-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="8b804-125">Kerberos et NTLM</span><span class="sxs-lookup"><span data-stu-id="8b804-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b804-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="8b804-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="8b804-127">Serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="8b804-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="8b804-128">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="8b804-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="8b804-129">Kerberos et NTLM</span><span class="sxs-lookup"><span data-stu-id="8b804-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b804-130">Si ces types d’authentifications ne sont pas désactivés au niveau du service, toutes les autres versions du client Lync ne seront pas en mesure de se connecter une fois que l’authentification à deux facteurs est activée dans le cadre de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="8b804-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="8b804-131">Découverte de service Lync</span><span class="sxs-lookup"><span data-stu-id="8b804-131">Lync Service Discovery</span></span>

<span data-ttu-id="8b804-132">Les enregistrements DNS utilisés par les clients internes et/ou externes pour détecter les services Lync doivent être configurés pour une résolution sur un serveur Lync qui n’est pas activé pour l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="8b804-133">Dans cette configuration, les utilisateurs de pools Lync qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas obligés d’entrer un code confidentiel pour s’authentifier, alors que les utilisateurs de pools Lync qui sont activés pour l’authentification à deux facteurs seront obligés d’entrer leur code confidentiel Authenticate.</span><span class="sxs-lookup"><span data-stu-id="8b804-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="8b804-134">Authentification Exchange</span><span class="sxs-lookup"><span data-stu-id="8b804-134">Exchange Authentication</span></span>

<span data-ttu-id="8b804-135">Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent constater que certaines fonctionnalités du client Lync ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="8b804-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="8b804-136">Cette fonctionnalité est actuellement à l’étude, car le client Lync ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration Exchange.</span><span class="sxs-lookup"><span data-stu-id="8b804-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="8b804-137">Contacts Lync</span><span class="sxs-lookup"><span data-stu-id="8b804-137">Lync Contacts</span></span>

<span data-ttu-id="8b804-138">Les utilisateurs de Lync qui sont configurés pour utiliser la fonctionnalité de magasin de contacts unifiée pourront constater que leurs contacts ne sont plus disponibles une fois que vous êtes connecté à l’aide de l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="8b804-139">Pour activer l’authentification à deux facteurs, vous devez utiliser l’applet de passe **Invoke-CsUcsRollback** pour supprimer les contacts des utilisateurs existants du magasin de contacts unifié et les stocker dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b804-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="8b804-140">Recherche de compétences</span><span class="sxs-lookup"><span data-stu-id="8b804-140">Skill Search</span></span>

<span data-ttu-id="8b804-141">Les clients qui ont configuré la fonction de recherche de compétences dans leur environnement Lync constateront que cette fonctionnalité ne fonctionne pas lorsque Lync est activé pour l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="8b804-142">Ce comportement est normal, car Microsoft SharePoint ne prend pas en charge l’authentification à deux facteurs pour le moment.</span><span class="sxs-lookup"><span data-stu-id="8b804-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="8b804-143">Informations d’identification Lync</span><span class="sxs-lookup"><span data-stu-id="8b804-143">Lync Credentials</span></span>

<span data-ttu-id="8b804-144">Il existe un certain nombre de considérations de déploiement impliquant des informations d’identification Lync enregistrées qui peuvent avoir un impact sur les utilisateurs qui sont configurés pour utiliser l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="8b804-145">Suppression des informations d’identification enregistrées</span><span class="sxs-lookup"><span data-stu-id="8b804-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="8b804-146">Les utilisateurs du client de bureau doivent utiliser l’option **Supprimer mes informations de connexion** dans le client Lync et supprimer leur dossier de profil SIP de\\%\\LocalAppData\\%\\Microsoft Office 15,0 Lync avant d’essayer de vous connecter pour la première fois à l’aide de l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="8b804-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="8b804-147">DisableNTCredentials</span></span>

<span data-ttu-id="8b804-148">Lorsque la méthode d’authentification Kerberos ou NTLM est utilisée, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="8b804-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="8b804-149">Dans le cas d’un déploiement standard de Lync Server 2013 sur lequel Kerberos et/ou NTLM est activé pour l’authentification, l’utilisateur ne doit pas entrer ses informations d’identification chaque fois qu’il se connecte.</span><span class="sxs-lookup"><span data-stu-id="8b804-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="8b804-150">Si les utilisateurs sont invités à entrer leurs informations d’identification avant leur code confidentiel, la clé de Registre **DisableNTCredentials** est peut être configurée involontairement sur les ordinateurs clients, éventuellement par le biais de la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="8b804-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="8b804-151">Pour empêcher l’invite supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs pour un pool donné à l’aide d’une stratégie de groupe :</span><span class="sxs-lookup"><span data-stu-id="8b804-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="8b804-152">HKEY\_stratégies\_\\\\\\logicielles\\locales Microsoft Office 15,0\\\\</span><span class="sxs-lookup"><span data-stu-id="8b804-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="8b804-153">REG\_DWORD : DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="8b804-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="8b804-154">Valeur : 0x0</span><span class="sxs-lookup"><span data-stu-id="8b804-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="8b804-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="8b804-155">SavePassword</span></span>

<span data-ttu-id="8b804-156">Lorsqu’un utilisateur se connecte à Lync pour la première fois, l’utilisateur est invité à enregistrer son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="8b804-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="8b804-157">Lorsqu’elle est sélectionnée, cette option permet le stockage du certificat client de l’utilisateur dans le magasin de certificats personnel et des informations d’identification Windows de l’utilisateur dans le Gestionnaire d’informations d’identification de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="8b804-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="8b804-158">Le paramètre de Registre **SavePassword** doit être désactivé lorsque Lync est configuré pour prendre en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="8b804-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="8b804-159">Pour empêcher les utilisateurs d’enregistrer leur mot de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs pour un pool donné à l’aide d’une stratégie de groupe :</span><span class="sxs-lookup"><span data-stu-id="8b804-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="8b804-160">HKEY\_logiciel\_\\utilisateur\\actuel Microsoft\\Office\\15,0\\Lync</span><span class="sxs-lookup"><span data-stu-id="8b804-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="8b804-161">REG\_DWORD : SavePassword</span><span class="sxs-lookup"><span data-stu-id="8b804-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="8b804-162">Valeur : 0x0</span><span class="sxs-lookup"><span data-stu-id="8b804-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="8b804-163">Relecture des jetons d’AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="8b804-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="8b804-p108">La fonctionnalité d’AD FS 2.0 de détection de relecture des jetons détecte et rejette les demandes de jeton multiples effectuées à l’aide d’un même jeton. Lorsqu’elle est activée, elle protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vérifiant que le même jeton n’est pas utilisé plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="8b804-p108">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="8b804-166">Cette fonctionnalité doit être activée dans les cas dans lesquels la sécurité constitue un aspect essentiel, par exemple, dans le cadre de l’utilisation des kiosques.</span><span class="sxs-lookup"><span data-stu-id="8b804-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="8b804-167">Pour plus d’informations sur la détection de relecture de jeton, voir recommandations en matière de planification et de déploiement [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)sécurisés d’AD FS 2,0 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="8b804-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="8b804-168">Accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="8b804-168">External User Access</span></span>

<span data-ttu-id="8b804-169">La configuration d’un proxy AD FS ou d’un proxy inverse pour prendre en charge l’authentification à deux facteurs de Lync à partir de réseaux externes n’est pas décrite dans les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="8b804-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

