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
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configuration des services ADFS (Active Directory Federation Services) pour Lync Server 2013 (AD FS 2,0)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

La section suivante décrit la configuration des services ADFS 2,0 (Active Directory Federation Services) pour prendre en charge l’authentification multifacteur. Pour plus d’informations sur l’installation d’AD FS 2,0, voir AD FS 2,0 Step-by-Step et How to [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)guides à l’adresse.

<div class="">


> [!NOTE]  
> Lors de l’installation d’AD FS 2,0, n’utilisez pas le gestionnaire Windows Server pour ajouter le rôle services ADFS (Active Directory Federation Services). Au lieu de cela, téléchargez et installez le package Active Directory Federation Services <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>2,0 RTW à l’adresse.



</div>

<div>


**Pour configurer AD FS pour l’authentification à deux facteurs**

1.  Connectez-vous à l’ordinateur AD FS 2,0 à l’aide d’un compte d’administrateur de domaine.

2.  Démarrez Windows PowerShell.

3.  À partir de la ligne de commande Windows PowerShell, exécutez la commande suivante :
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Établissez un partenariat avec chaque Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : le directeur de 2013 juillet, le pool d’entreprise et le serveur Standard Edition Server qui seront activés pour l’authentification passive en exécutant la commande suivante, en remplaçant le nom de serveur spécifique à votre déploiement :
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Dans le menu Outils d’administration, lancez la console de gestion AD FS 2,0.

6.  Développez **relations** \> d’approbation de **partie**de confiance.

7.  Vérifiez qu’une nouvelle approbation a été créée pour votre Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : juillet 2013 pool d’entreprise ou serveur Standard Edition.

8.  Créez et attribuez une règle d’autorisation d’émission pour votre approbation de partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Créez et affectez une règle de transformation d’émission pour votre approbation de partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Dans la console de gestion AD FS 2,0, cliquez avec le bouton droit sur votre approbation de partie de confiance et sélectionnez **modifier les règles de revendication**.

11. Sélectionnez l’onglet **règles d’autorisation d’émission** et vérifiez que la nouvelle règle d’autorisation a bien été créée.

12. Sélectionnez l’onglet **règles de transformation d’émission** et vérifiez que la nouvelle règle de transformation a bien été créée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

