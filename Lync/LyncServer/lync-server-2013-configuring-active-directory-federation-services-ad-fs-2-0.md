---
title: 'Lync Server 2013 : configuration des services ADFS (Active Directory Federation Services) (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c82c1ad2072f5f8611660efc44a502249f26d21b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="16822-102">Configuration des services ADFS (Active Directory Federation Services) pour Lync Server 2013 (AD FS 2,0)</span><span class="sxs-lookup"><span data-stu-id="16822-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16822-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="16822-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="16822-104">La section suivante décrit la configuration des services ADFS 2,0 (Active Directory Federation Services) pour prendre en charge l’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="16822-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="16822-105">Pour plus d’informations sur l’installation d’AD FS 2,0, voir AD FS 2,0 Step-by-Step et How to [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)guides à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="16822-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="16822-106">Lors de l’installation d’AD FS 2,0, n’utilisez pas le gestionnaire Windows Server pour ajouter le rôle services ADFS (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="16822-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="16822-107">Au lieu de cela, téléchargez et installez le package Active Directory Federation Services <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>2,0 RTW à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="16822-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="16822-108">**Pour configurer AD FS pour l’authentification à deux facteurs**</span><span class="sxs-lookup"><span data-stu-id="16822-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="16822-109">Connectez-vous à l’ordinateur AD FS 2,0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="16822-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="16822-110">Démarrez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16822-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="16822-111">À partir de la ligne de commande Windows PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="16822-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="16822-112">Établissez un partenariat avec chaque Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : le directeur de 2013 juillet, le pool d’entreprise et le serveur Standard Edition Server qui seront activés pour l’authentification passive en exécutant la commande suivante, en remplaçant le nom de serveur spécifique à votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="16822-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="16822-113">Dans le menu Outils d’administration, lancez la console de gestion AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="16822-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="16822-114">Développez **relations** \> d’approbation de **partie**de confiance.</span><span class="sxs-lookup"><span data-stu-id="16822-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="16822-115">Vérifiez qu’une nouvelle approbation a été créée pour votre Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : juillet 2013 pool d’entreprise ou serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="16822-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="16822-116">Créez et attribuez une règle d’autorisation d’émission pour votre approbation de partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="16822-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="16822-117">Créez et affectez une règle de transformation d’émission pour votre approbation de partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="16822-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="16822-118">Dans la console de gestion AD FS 2,0, cliquez avec le bouton droit sur votre approbation de partie de confiance et sélectionnez **modifier les règles de revendication**.</span><span class="sxs-lookup"><span data-stu-id="16822-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="16822-119">Sélectionnez l’onglet **règles d’autorisation d’émission** et vérifiez que la nouvelle règle d’autorisation a bien été créée.</span><span class="sxs-lookup"><span data-stu-id="16822-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="16822-120">Sélectionnez l’onglet **règles de transformation d’émission** et vérifiez que la nouvelle règle de transformation a bien été créée.</span><span class="sxs-lookup"><span data-stu-id="16822-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

