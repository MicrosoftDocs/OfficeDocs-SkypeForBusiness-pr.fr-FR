---
title: Gérer les paramètres de configuration du serveur d’inscriptions dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Résumé : Gérez les paramètres de configuration du serveur d’inscriptions pour Skype Entreprise Server.'
ms.openlocfilehash: a1cd1048ea37a249126ec892560312a482459d44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119573"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c6519-103">Gérer les paramètres de configuration du serveur d’inscriptions dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c6519-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c6519-104">**Résumé :** Gérer les paramètres de configuration du serveur d’inscriptions pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="c6519-105">Vous pouvez utiliser le serveur d’inscriptions pour configurer les méthodes d’authentification du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="c6519-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="c6519-106">Le protocole d’authentification que vous spécifiez détermine le type de défis que les serveurs du pool doivent relever aux clients.</span><span class="sxs-lookup"><span data-stu-id="c6519-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="c6519-107">Les protocoles disponibles sont :</span><span class="sxs-lookup"><span data-stu-id="c6519-107">The available protocols are:</span></span>
  
- <span data-ttu-id="c6519-108">**Kerberos** Il s’agit du schéma d’authentification par mot de passe le plus fort disponible pour les clients, mais il est généralement disponible uniquement pour les clients d’entreprise, car il nécessite une connexion client à un centre de distribution de clés (contrôleur de domaine Kerberos).</span><span class="sxs-lookup"><span data-stu-id="c6519-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="c6519-109">Ce paramètre est approprié si le serveur authentifier uniquement les clients d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6519-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="c6519-110">**NTLM** Il s’agit de l’authentification par mot de passe disponible pour les clients qui utilisent un schéma de hachage challenge-response sur le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c6519-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="c6519-111">Il s’agit de la seule forme d’authentification disponible pour les clients sans connectivité à un centre de distribution de clés (contrôleur de domaine Kerberos), comme les utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="c6519-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="c6519-112">Si un serveur authentifier uniquement les utilisateurs distants, vous devez choisir NTLM.</span><span class="sxs-lookup"><span data-stu-id="c6519-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="c6519-113">**Authentification de certificat** Il s’agit de la nouvelle méthode d’authentification lorsque le serveur doit obtenir des certificats auprès de clients Lync Phone Edition, de téléphones de partie commune, de Skype Entreprise et de l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="c6519-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="c6519-114">Sur les clients Lync Phone Edition, une fois qu’un utilisateur s’est correctement authentifié en fournissant un code confidentiel, Skype Entreprise Server met ensuite en service l’URI SIP sur le téléphone et met en service un certificat signé Skype Entreprise Server ou un certificat d’utilisateur qui identifie Joe (Ex: SN=joe@contoso.com ) sur le téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6519-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="c6519-115">Ce certificat est utilisé pour l’authentification auprès du serveur d’inscriptions et des services Web.</span><span class="sxs-lookup"><span data-stu-id="c6519-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6519-p105">Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c6519-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="c6519-120">Si vous utilisez des clients d’application du Windows Store Lync, vous devez activer l’authentification par certificat.</span><span class="sxs-lookup"><span data-stu-id="c6519-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="c6519-121">Pour créer de nouveaux paramètres de configuration du bureau d’enregistrement d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="c6519-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="c6519-122">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c6519-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c6519-124">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.</span><span class="sxs-lookup"><span data-stu-id="c6519-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c6519-125">Dans la page **Du bureau d’enregistrement,** cliquez sur **Nouveau**</span><span class="sxs-lookup"><span data-stu-id="c6519-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="c6519-126">Dans **Sélectionner un service,** cliquez sur le service auquel le bureau d’inscriptions doit être appliqué, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="c6519-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="c6519-127">Dans **Nouveau paramètre du bureau d’enregistrement,** sélectionnez une ou plusieurs des fonctionnalités suivantes en fonction des fonctionnalités des clients et de la prise en charge dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="c6519-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c6519-128">**Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c6519-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="c6519-129">**Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.</span><span class="sxs-lookup"><span data-stu-id="c6519-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="c6519-130">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="c6519-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="c6519-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c6519-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="c6519-132">Modifier les paramètres de configuration du bureau d’enregistrement d’inscriptions existant</span><span class="sxs-lookup"><span data-stu-id="c6519-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="c6519-133">Vous pouvez utiliser le serveur d’inscriptions pour configurer les protocoles d’authentification du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="c6519-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c6519-p106">Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c6519-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="c6519-138">Procédez comme suit pour modifier un serveur d’inscription existant.</span><span class="sxs-lookup"><span data-stu-id="c6519-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="c6519-139">Pour modifier les paramètres de configuration du bureau d’enregistrement d’inscriptions existant</span><span class="sxs-lookup"><span data-stu-id="c6519-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="c6519-140">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c6519-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c6519-142">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.</span><span class="sxs-lookup"><span data-stu-id="c6519-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c6519-143">Dans la page **Serveur d’inscriptions**, cliquez sur un service, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="c6519-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c6519-144">Dans **Modifier le paramètre du serveur d’inscriptions**, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="c6519-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c6519-145">**Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c6519-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="c6519-146">**Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.</span><span class="sxs-lookup"><span data-stu-id="c6519-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="c6519-147">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="c6519-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="c6519-148">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c6519-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="c6519-149">Pour supprimer les paramètres de configuration du bureau d’enregistrement d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="c6519-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="c6519-150">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c6519-151">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c6519-152">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.</span><span class="sxs-lookup"><span data-stu-id="c6519-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c6519-153">Dans la page **Serveur d’inscriptions**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="c6519-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="c6519-154">Dans la liste, cliquez sur le serveur d’inscriptions souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c6519-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="c6519-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6519-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c6519-156">Suppression des paramètres de configuration du bureau d’enregistrement d’inscriptions Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="c6519-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c6519-157">Vous pouvez supprimer les paramètres de configuration du bureau d’enregistrement d’inscriptions à l Windows PowerShell applet **remove-CsProxyConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="c6519-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="c6519-158">Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6519-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c6519-159">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="c6519-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c6519-160">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6519-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="c6519-161">Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="c6519-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="c6519-162">La commande suivante supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="c6519-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="c6519-163">Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="c6519-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="c6519-164">La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :</span><span class="sxs-lookup"><span data-stu-id="c6519-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="c6519-165">Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM</span><span class="sxs-lookup"><span data-stu-id="c6519-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="c6519-166">La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :</span><span class="sxs-lookup"><span data-stu-id="c6519-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="c6519-167">Pour plus d’informations, [voir Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6519-167">For details, see [Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
