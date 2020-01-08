---
title: 'Lync Server 2013 : configuration des services de fédération Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a88fb9db7109bdd2a2938f8f9624b4fd0f369fd9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configuration des services ADFS 2,0 (Active Directory Federation Services) pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Cette section décrit la configuration d’Active Directory Federation Services (AD FS 2.0) pour prendre en charge l’authentification multifacteur. Pour plus d’informations sur l’installation d’AD FS 2,0, consultez la rubrique AD FS 2,0 étape par étape et comment les [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)guides.

<div class="">


> [!NOTE]  
> Lorsque vous installez AD FS 2.0, vous ne devez pas utiliser le Gestionnaire de serveur Windows pour ajouter le rôle Active Directory Federation Services. Au lieu de cela, téléchargez et installez le package de services ADFS ( <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory Federation Services) 2,0 à l’adresse.



</div>

<div>


**Pour configurer AD FS pour l’authentification à deux facteurs**

1.  Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2.  Lancez Windows PowerShell.

3.  À partir de la ligne de commande Windows PowerShell, exécutez la commande suivante :
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Établissez un partenariat avec chaque 2013 Lync Server avec des mises à jour cumulatives pour Lync Server 2013 : le directeur 2013 de juillet, le pool d’entreprise et le serveur Standard Edition Server qui seront activés pour l’authentification passive en exécutant la commande suivante, en remplaçant le nom du serveur propre à votre déploiement :
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Dans le menu Outils d’administration, lancez la console de gestion AD FS 2.0.

6.  Développez **relations d’approbation** \> de confiance entre les **parties**.

7.  Vérifiez qu’une nouvelle approbation a été créée pour votre Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 du pool d’entreprise.

8.  Créez et affectez une règle d’autorisation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Créez et affectez une règle de transformation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre relation d’approbation de la partie de confiance, puis sélectionnez **Modifier les règles de revendication**.

11. Sélectionnez l’onglet **Règles d’autorisation d’émission**, puis vérifiez que la règle d’autorisation a été correctement créée.

12. Sélectionnez l’onglet **Règles de transformation d’émission**, puis vérifiez que la règle de transformation d’émission a été créée correctement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

