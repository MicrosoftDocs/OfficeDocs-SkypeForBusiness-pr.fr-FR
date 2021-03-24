---
title: Configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365.
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095088"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="56a8b-103">Configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="56a8b-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="56a8b-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="56a8b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="56a8b-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="56a8b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="56a8b-106">Découvrez comment configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="56a8b-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="56a8b-107">Une fois l’installation de La version Cloud Connector de Skype Entreprise terminée, effectuez les étapes de cette section pour configurer votre déploiement et le connecter à votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="56a8b-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="56a8b-108">Configurer les paramètres de pare-feu</span><span class="sxs-lookup"><span data-stu-id="56a8b-108">Configure firewall settings</span></span>

<span data-ttu-id="56a8b-109">Configurez les paramètres de pare-feu pour vos paramètres de pare-feu interne et externe pour que votre réseau de périmètre ouvre les ports requis, comme décrit dans [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) dans [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="56a8b-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="56a8b-110">Configurer des passerelles de réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="56a8b-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="56a8b-111">Configurer des trunks sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances.</span><span class="sxs-lookup"><span data-stu-id="56a8b-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="56a8b-112">Étant donné que le nom de pool est le même pour tous les serveurs du pool, chaque trunk doit pointer vers un nom de groupe ou une adresse IP du serveur de médiation au lieu du nom de pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="56a8b-113">Les trunks doivent être définies dans la même priorité.</span><span class="sxs-lookup"><span data-stu-id="56a8b-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="56a8b-114">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devez configurer les passerelles et les serveurs de médiation pour prendre en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a8b-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="56a8b-115">Exporte l’autorité de contrôle d’autorité de contrôle racine à partir de l’ordinateur Active Directory cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56a8b-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="56a8b-116">Suivez les instructions du fournisseur de passerelle PSTN pour importer l’ac racine.</span><span class="sxs-lookup"><span data-stu-id="56a8b-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="56a8b-117">Importez le certificat d’ac racine pour le certificat émis sur votre passerelle sur les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="56a8b-118">Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service d’autorité de certification qui s’exécute sur l’ordinateur Active Directory cloud Connector comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a8b-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="56a8b-119">Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="56a8b-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="56a8b-120">Pour obtenir des instructions détaillées, voir [Modèles de certificat.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="56a8b-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="56a8b-121">Demandez un certificat à l’aide du logiciel en ligne Certificat en sélectionnant le modèle de serveur Web que vous avez activé.</span><span class="sxs-lookup"><span data-stu-id="56a8b-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="56a8b-122">Veillez à ajouter le nom commun dans l’objet et le nom DNS dans l’autre nom avec le nom de domaine complet de la passerelle, et confirmez sur la clé privée que Rendre la clé privée exportable est sélectionné sous les options de clé.</span><span class="sxs-lookup"><span data-stu-id="56a8b-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="56a8b-123">Exportez le certificat SSL avec une clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="56a8b-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="56a8b-124">Mettre à jour le domaine pour votre client</span><span class="sxs-lookup"><span data-stu-id="56a8b-124">Update the domain for your tenant</span></span>

<span data-ttu-id="56a8b-125">Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="56a8b-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="56a8b-126">Pour plus d’informations sur la façon de configurer votre domaine dans Microsoft 365 ou Office 365, voir Ajouter un domaine à [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="56a8b-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="56a8b-127">Ajouter des enregistrements DNS pour votre edge</span><span class="sxs-lookup"><span data-stu-id="56a8b-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="56a8b-128">Ajoutez les enregistrements DNS suivants à votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="56a8b-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="56a8b-129">Pour plus d’informations sur l’ajout d’enregistrements DNS, voir Ajouter ou modifier des enregistrements DNS personnalisés dans [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)</span><span class="sxs-lookup"><span data-stu-id="56a8b-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="56a8b-130">Ajoutez un enregistrement DNS A pour le edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="56a8b-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="56a8b-131">Les enregistrements SRV sont automatiquement créés par Microsoft 365 ou Office 365 et les scripts de déploiement.</span><span class="sxs-lookup"><span data-stu-id="56a8b-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="56a8b-132">Confirmez que vous pouvez rechercher les deux services SIP suivants sur le edge : sip et \_ \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="56a8b-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="56a8b-134">Configurer la connectivité hybride entre Cloud Connector Edition et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="56a8b-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="56a8b-135">Pour configurer la connectivité hybride entre votre déploiement Skype Entreprise, version Cloud Connector et votre organisation Microsoft 365 ou Office 365, exécutez l’cmdlet suivante dans une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="56a8b-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="56a8b-136">Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur [pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="56a8b-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="56a8b-137">L’cmdlet définit le FQDN externe du edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="56a8b-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="56a8b-138">Dans la première des commandes, celle-ci doit être celle du rôle \<External Access Edge FQDN\> Edge d’accès SIP.</span><span class="sxs-lookup"><span data-stu-id="56a8b-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="56a8b-139">Par défaut, ce doit être ap. \<Domain Name\> .</span><span class="sxs-lookup"><span data-stu-id="56a8b-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="56a8b-140">Le FQDN du edge d’accès externe utilisé pour la destination homologue doit être affecté à un site PSTN qui ne sera utilisé que comme base au cas où un utilisateur n’est pas affecté à un site PSTN.</span><span class="sxs-lookup"><span data-stu-id="56a8b-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="56a8b-141">Pour plus d’informations, voir [Déployer un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et Déployer plusieurs sites dans Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="56a8b-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="56a8b-142">Configurer des passerelles PSTN</span><span class="sxs-lookup"><span data-stu-id="56a8b-142">Set up PSTN gateways</span></span>

<span data-ttu-id="56a8b-143">Configurer des trunks sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances.</span><span class="sxs-lookup"><span data-stu-id="56a8b-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="56a8b-144">Chaque trunk doit pointer vers un nom de groupe ou une adresse IP de serveur de médiation au lieu du nom de pool de serveurs de médiation, car le nom de pool est le même pour tous les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="56a8b-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="56a8b-145">Les trunks doivent être définies dans la même priorité.</span><span class="sxs-lookup"><span data-stu-id="56a8b-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="56a8b-146">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devez configurer les passerelles et les serveurs de médiation pour prendre en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a8b-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="56a8b-147">Exporte l’autorité de contrôle d’autorité de contrôle racine à partir de l’ordinateur Active Directory cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56a8b-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="56a8b-148">Suivez les instructions du fournisseur de passerelle PSTN pour importer l’ac racine.</span><span class="sxs-lookup"><span data-stu-id="56a8b-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="56a8b-149">Importez le certificat d’ac racine pour le certificat émis sur votre passerelle sur les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="56a8b-150">Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service d’autorité de certification qui s’exécute sur l’ordinateur Active Directory cloud Connector comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a8b-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="56a8b-151">Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="56a8b-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="56a8b-152">Pour obtenir des instructions détaillées, voir [Modèles de certificat.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="56a8b-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="56a8b-153">Demandez un certificat à l’aide du logiciel en ligne Certificat en sélectionnant le modèle de serveur Web que vous avez activé.</span><span class="sxs-lookup"><span data-stu-id="56a8b-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="56a8b-154">Veillez à ajouter le nom commun dans l’objet et le nom DNS dans l’autre nom avec le nom de domaine complet de la passerelle, et confirmez sur la clé privée que Rendre la clé privée exportable est sélectionné sous les options de clé.</span><span class="sxs-lookup"><span data-stu-id="56a8b-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="56a8b-155">Exportez le certificat SSL avec une clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="56a8b-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="56a8b-156">Les passerelles PSTN d’un site PSTN ne doivent se connecter qu’aux serveurs de médiation du même site.</span><span class="sxs-lookup"><span data-stu-id="56a8b-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="56a8b-157">Configurer vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="56a8b-157">Set up your users</span></span>

<span data-ttu-id="56a8b-158">Connectez-vous au Centre d’administration Microsoft 365, ajoutez les utilisateurs qui seront activés pour les services vocaux en ligne et attribuez une licence E5 ou un module de système téléphonique à la licence E3 à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="56a8b-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="56a8b-159">Pour plus d’informations sur l’ajout d’utilisateurs, voir Ajouter des utilisateurs [à Microsoft 365 pour les entreprises.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="56a8b-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="56a8b-160">Activer les utilisateurs pour les services vocaux et de messagerie vocale du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="56a8b-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="56a8b-161">Après avoir ajouté vos utilisateurs à Microsoft 365 ou Office 365, activez leurs comptes pour les services vocaux du système téléphonique, y compris la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="56a8b-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="56a8b-162">Pour activer ces fonctionnalités, vous devez vous connecter à votre organisation Microsoft 365 ou Office 365 avec un compte qui est un rôle d’administrateur général et être en mesure d’exécuter PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="56a8b-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="56a8b-163">Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur [pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="56a8b-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="56a8b-164">Affectez la stratégie à votre utilisateur et configurez le numéro de téléphone vocal de l’utilisateur, que vous spécifiez avec la valeur du **paramètre Identity** :</span><span class="sxs-lookup"><span data-stu-id="56a8b-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="56a8b-165">Une identité d’utilisateur peut être spécifiée à l’aide de l’adresse SIP de l’utilisateur, du nom d’utilisateur principal (UPN) ou du nom complet Active Directory de l’utilisateur (par exemple, « Bob Kelly »).</span><span class="sxs-lookup"><span data-stu-id="56a8b-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="56a8b-166">Le caractère astérisque ( ) peut également être utilisé avec le nom complet comme \* identité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56a8b-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="56a8b-167">Par exemple, l’identité « Smith » renvoie tous les utilisateurs dont le nom complet se termine par la valeur de chaîne \* « Smith ».</span><span class="sxs-lookup"><span data-stu-id="56a8b-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="56a8b-168">Vous pouvez ensuite vérifier que les utilisateurs ont été ajoutés et activés à l’aide du script suivant :</span><span class="sxs-lookup"><span data-stu-id="56a8b-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="56a8b-169">Vous devez décider si vos utilisateurs doivent être en mesure d’effectuer des appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="56a8b-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="56a8b-170">Par défaut, les appels internationaux sont activés.</span><span class="sxs-lookup"><span data-stu-id="56a8b-170">By default, international calling is enabled.</span></span> <span data-ttu-id="56a8b-171">Vous pouvez désactiver ou activer la numérotation à l’international à l’aide du Centre d’administration Skype Entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="56a8b-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="56a8b-172">Pour désactiver les appels internationaux par utilisateur, exécutez l’cmdlet suivante dans Skype Entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="56a8b-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="56a8b-173">Pour réactiver les appels internationaux par utilisateur après sa désactivation, exécutez la même cmdlet, mais modifiez la valeur de **PolicyName** en *InternationalCallsAllowed*  .</span><span class="sxs-lookup"><span data-stu-id="56a8b-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="56a8b-174">Affecter des utilisateurs à des sites PSTN</span><span class="sxs-lookup"><span data-stu-id="56a8b-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="56a8b-175">Utilisez powerShell distant client pour affecter un site aux utilisateurs, même si vous n’avez déployé qu’un seul site.</span><span class="sxs-lookup"><span data-stu-id="56a8b-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="56a8b-176">Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur [pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="56a8b-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="56a8b-177">Si aucun site PSTN n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement Skype Entreprise, version Cloud Connector et votre organisation Microsoft 365 ou Office 365, utilisera le niveau de client par défaut 1 (destination homologue) pour que les appels soient effectués.</span><span class="sxs-lookup"><span data-stu-id="56a8b-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="56a8b-178">Configurer les paramètres du serveur de médiation hybride en ligne</span><span class="sxs-lookup"><span data-stu-id="56a8b-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="56a8b-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="56a8b-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="56a8b-180">Lorsqu’un appel P2P est recalcalé à une conférence PSTN, le serveur de conférence Skype Entreprise Online envoie une invitation au serveur de médiation Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56a8b-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="56a8b-181">Pour vous assurer que Microsoft 365 ou Office 365 peut router cette invitation avec succès, vous devez configurer un paramètre dans votre client en ligne pour chaque serveur de médiation Cloud Connector comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a8b-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="56a8b-182">Créez un utilisateur dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56a8b-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="56a8b-183">Utilisez le nom d’utilisateur que vous souhaitez, tel que « MediationServer1 ».</span><span class="sxs-lookup"><span data-stu-id="56a8b-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="56a8b-184">Utilisez le domaine SIP par défaut de Cloud Connector (le premier domaine SIP dans le fichier .ini) comme domaine utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56a8b-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="56a8b-185">Veuillez noter que l’attribution de licence n’est requise que pour la propagation de l’utilisateur dans l’annuaire Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="56a8b-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="56a8b-186">Attribuez une licence Microsoft 365 ou Office 365 (par exemple E5) au compte que vous créez, autorisez jusqu’à une heure pour que les modifications se propagent, vérifiez que les comptes d’utilisateur ont été correctement mis en service dans l’annuaire Skype Entreprise Online en exécutant l’cmdlet suivante, puis supprimez la licence de ce compte.</span><span class="sxs-lookup"><span data-stu-id="56a8b-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="56a8b-187">Démarrez une session PowerShell distante Azure AD client à l’aide de vos informations d’identification d’administrateur global ou utilisateur, puis exécutez l’cmdlet suivante pour définir le service du compte d’utilisateur Azure AD configuré à l’étape 1 sur « HybridMediationServer » :</span><span class="sxs-lookup"><span data-stu-id="56a8b-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="56a8b-188">Démarrez une session PowerShell distante Skype Entreprise client à l’aide de vos informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour définir le nom de domaine complet du serveur de médiation et du serveur Edge sur ce compte d’utilisateur, en remplaçant par le nom complet de l’utilisateur pour le compte que vous avez créé à l’étape \<DisplayName\> 1 :</span><span class="sxs-lookup"><span data-stu-id="56a8b-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="56a8b-189">Pour l’identité, utilisez le nom complet du compte d’utilisateur que vous avez créé pour ce serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="56a8b-190">Pour  *mediationServerFQDN,*  utilisez le nom de groupe interne défini pour votre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="56a8b-191">Pour  *edgeServerExternalFQDN,*  utilisez le nom de groupe externe défini pour le proxy d’accès au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="56a8b-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="56a8b-192">S’il existe plusieurs sites PSTN Cloud Connector, choisissez le FQDN du proxy d’accès du serveur Edge affecté au site où se trouve le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="56a8b-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="56a8b-193">S’il existe plusieurs serveurs de médiation Cloud Connector (plusieurs sites, haute haute qualité), répétez les étapes précédentes pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="56a8b-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
