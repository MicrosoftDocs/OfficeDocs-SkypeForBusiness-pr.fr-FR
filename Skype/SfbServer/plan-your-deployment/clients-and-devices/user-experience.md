---
title: Planifier l’interface du client Skype entreprise 2015 pour vos utilisateurs
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Résumé : en savoir plus sur le nouveau Skype entreprise et les étapes à suivre pour préparer votre environnement et vos utilisateurs pour la mise à jour, que vous utilisiez Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015, Lync Server 2013 ou Lync Server 2010.'
ms.openlocfilehash: afd0f9f8a764ef9430d9ac1a9887a872c02fedd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803524"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planifier l’interface du client Skype entreprise 2015 pour vos utilisateurs
 
**Résumé :** Découvrez le nouveau Skype entreprise et les étapes à suivre pour préparer votre environnement et vos utilisateurs pour la mise à jour, que vous utilisiez Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015, Lync Server 2013 ou Lync Server 2010.
  
Le 14 avril, 2015 Office Update pour Lync 2013 inclut la nouvelle interface utilisateur Skype entreprise. Cette mise à jour permet aux administrateurs de contrôler l’apparence du client et de conserver l’utilisation du client 2013 Lync ou d’utiliser l’amélioration du client Skype entreprise. Le client Skype entreprise a effectivement remplacé le client 2013 Lync et a ajouté la possibilité pour les administrateurs de choisir entre l’environnement client Lync existant et le nouveau client Skype entreprise. Pour plus d’informations sur cette mise à jour, voir la [mise à jour 2015 du 14 avril pour Lync 2013 (Skype entreprise) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Le 12 2015, la mise à jour mensuelle d’Office inclut la mise à jour du client Skype entreprise. De nombreux clients n’appliquant pas la mise à jour d’avril recevront la mise à jour du 12 mai pour Office 2013. Les informations de cette rubrique vous aideront à préparer votre organisation, votre environnement et vos utilisateurs pour la mise à jour du client. Pour faciliter cette transition pour vos utilisateurs et vos équipes de support, utilisez les informations de cette rubrique pour mieux déterminer l’expérience client que vous souhaitez utiliser et apportez les modifications nécessaires à votre environnement avant de déployer la mise à jour du client dans votre organisation.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Préparation de votre environnement pour le client Skype Entreprise](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> L’interface du client 2013 de Lync n’est pas disponible pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client 2013 Lync, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro 16 ; par exemple : 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quelle expérience client voulez-vous pour vos utilisateurs ?
<a name="clientexperience"> </a>

Le nouveau client Skype entreprise vous permet de contrôler l’interface utilisateur qu’ils obtiennent, qu’il s’agisse de Lync ou de Skype entreprise. L’environnement client par défaut varie selon que vous utilisez Lync ou Skype entreprise local ou en ligne. Si vous utilisez Skype entreprise Online (Lync Online) aujourd’hui avec Office 365 ProPlus, Office 365 Business Premium ou Office 2013, l’expérience client Skype entreprise mise à jour, inspirée de l’apparence de Skype, sera l’expérience utilisateur par défaut. Si vous utilisez la version locale de Lync Server dans le monde, l’interface utilisateur de Lync sera utilisée par défaut.
  
Vous pouvez configurer l’expérience client de vos utilisateurs à l’aide de stratégies client. Une stratégie client est un ensemble de paramètres de configuration appliqués aux utilisateurs lorsqu’ils se connectent à Lync ou à Skype entreprise.
  
### <a name="skype-for-business-client-experience"></a>Expérience client Skype Entreprise

Outre l’ensemble des fonctionnalités de Lync, Skype entreprise fournit de nouvelles fonctionnalités qui vous permettent d’utiliser les commandes et les icônes habituelles de Skype. Certaines nouvelles fonctions de Skype entreprise ne sont disponibles qu’avec le nouveau client Skype entreprise. Pour en savoir plus sur les nouvelles fonctionnalités de Skype entreprise, reportez-vous à la rubrique [découvrir Skype entreprise](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Expérience client Lync

L’expérience client Lync est très similaire à l’expérience client Lync 2013 que vos utilisateurs connaissent déjà, mais voici quelques modifications que vous voudrez sûrement présenter à vos utilisateurs. Pour plus d’informations sur les différences entre l’utilisation du client Lync et le client 2013 Lync, reportez-vous à la rubrique [pourquoi est-ce que je vois Skype entreprise alors que j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkId=544712) et les liens supplémentaires plus loin dans cette rubrique.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Préparation de votre environnement pour le client Skype Entreprise
<a name="usinglync"> </a>

Pour préparer votre environnement pour la mise à jour du client, vous devez effectuer quelques petites opérations. Avant de commencer à apporter des modifications à la configuration de l’utilisation du client, vous devez d’abord vérifier que vous utilisez une version de Skype entreprise Server ou de Lync Server qui prend en charge les paramètres de stratégie de client.
  
Une fois que vous avez confirmé que vous utilisez une version de Skype entreprise Server ou Lync Server qui prend en charge les paramètres de stratégie pour contrôler l’utilisation du client, vous devez configurer les paramètres de stratégie dans votre environnement. Les étapes spécifiques que vous devez suivre varient en fonction de la version de Skype entreprise Server ou de Lync Server que vous utilisez, et de la manière dont vos utilisateurs sont en local ou en ligne. 
  
Vous devrez apporter ces modifications avant que la mise à jour du client ne soit remise aux utilisateurs pour que vous puissiez contrôler l’utilisation du client dès la première ouverture du client Skype entreprise. Les tableaux suivants vous permettent de vous familiariser avec les étapes que vous devez suivre pour configurer votre environnement pour l’environnement client souhaité pour vos utilisateurs.
  
|**Deployment**|**Expérience client Skype Entreprise**|**Expérience client Lync**|
|:-----|:-----|:-----|
|Skype Entreprise Online  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utilisation de l’expérience client Lync avec Skype Entreprise Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Entreprise Server 2015  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utilisation de l’expérience client Lync avec Skype Entreprise Server en local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 et Lync Server 2010  <br/> |[Utiliser le client Skype avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#SkypewithLynconprem) <br/> |[Utiliser l’environnement client Lync avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utiliser le client Skype avec Lync Server 2013 ou Lync Server 2010 en local
<a name="SkypewithLynconprem"> </a>

Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, assurez-vous que vous utilisez une version de Lync Server qui prend en charge les paramètres de stratégie de client.
  
- **Lync server 2013** -vous devez exécuter la mise à jour cumulative 2014 de décembre pour lync Server 2013 ou une version ultérieure. Pour plus d’informations, consultez [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** -vous devez exécuter la mise à jour cumulative de février 2015 (4.0.7577.710) pour lync Server 2010 ou une version ultérieure. Pour plus d’informations, consultez [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Étape 2 :** Ensuite, utilisez une stratégie client pour définir l’utilisation du client Skype avec le client Skype entreprise. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client.
  
  **Option 1 :** définissez l’expérience client Skype à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais les stratégies de niveau utilisateur et site ont priorité sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Skype. Cela vous permet d’affecter l’expérience client Skype uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3 :** créez une stratégie à affecter aux utilisateurs, qui inclut le paramètre de l’expérience client Skype. Commencez par créer la stratégie du client et indiquez le nom de la stratégie sous forme de valeur du paramètre **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Ensuite, affectez la stratégie aux utilisateurs en utilisant le nom de la stratégie (la valeur utilisée pour le paramètre **Identity**) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Étape 3 :** Une fois que vous avez configuré vos stratégies de client, déployez le client Skype entreprise, créez 4711,1002 (avril, 2015) ou version ultérieure.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utiliser l’environnement client Lync avec Lync Server 2013 ou Lync Server 2010 en local
<a name="LyncwithLynconprem"> </a>

Il s’agit de l’interface par défaut lors du déploiement du client Skype entreprise dans un déploiement local de Lync Server. Vous n’avez pas besoin de configurer des stratégies client pour utiliser l’expérience client Lync, mais vous avez la possibilité de contrôler le comportement lors de la première utilisation du client. Par défaut, lorsque les utilisateurs lancent le client Skype entreprise pour la première fois, l’interface du client Skype est utilisée et une notification s’affiche aux utilisateurs qui souhaitent qu’ils redémarrent le client pour obtenir l’interface du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client en modifiant le Registre système sur les ordinateurs du client. Pour connaître les étapes que vous devez effectuer avant de déployer le client Skype entreprise, reportez-vous à l’une des rubriques suivantes :
  
- **Lync server 2013**, voir [configurer l’interface client avec Skype entreprise dans Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** reportez-vous [à la rubrique Configuration de l’interface client avec Skype entreprise dans Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Server en local
<a name="LyncwithSfBServer"> </a>

Suivez les étapes décrites dans cette section si vous voulez configurer l’environnement client Lync dans un déploiement local de Skype entreprise Server.
  
Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, déployez Skype entreprise Server.
  
 **Étape 2 :** Ensuite, utilisez une stratégie client pour définir l’utilisation du client Lync avec le client Skype entreprise. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client.
  
 **Option 1 :** définissez l’expérience client Lync à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais les stratégies de niveau utilisateur et site ont priorité sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3 :** créez une stratégie à affecter aux utilisateurs, qui inclut le paramètre de l’expérience client Lync. Commencez par créer la stratégie du client et indiquez le nom de la stratégie sous forme de valeur du paramètre **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Ensuite, affectez la stratégie aux utilisateurs en utilisant le nom de la stratégie (la valeur utilisée pour le paramètre **Identity**) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Étape 3 :** par défaut, lorsque les utilisateurs lancent le client Skype entreprise pour la première fois, l’interface du client Skype est utilisée et une notification s’affiche aux utilisateurs leur demandant de redémarrer le client pour obtenir l’utilisation du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client, en modifiant le Registre système sur les ordinateurs du client. Pour connaître la procédure à suivre avant de déployer le client Skype entreprise, voir [configurer l’interface client avec Skype entreprise](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Étape 4 :** Une fois que vous avez configuré vos stratégies de client, déployez le client Skype entreprise, créez 4711,1002 (avril, 2015) ou version ultérieure.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Online
<a name="LyncwithSfBO"> </a>

Suivez les étapes décrites dans cette section si vous voulez configurer l’utilisation du client Lync et vous utilisez Skype entreprise online.
  
Si vous utilisez Skype entreprise Online, vous pouvez toujours utiliser l’interface client de Lync avec le client Skype entreprise dans votre organisation à l’aide de Remote PowerShell pour configurer les stratégies client. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client. Notez que les noms de stratégie et de paramètre sont différents de ceux que vous utilisez pour configurer l’utilisation du client lorsque vous utilisez Skype entreprise ou Lync Server en local.
  
 **Option 1 :** Définir l’utilisation du client Lync à l’aide d’une stratégie globale. Notez que les stratégies de client et de site appliquées aux utilisateurs seront prioritaires sur une stratégie globale.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3 :** Utilisez une instance de stratégie personnalisée qui inclut le paramètre de l’environnement client Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Une fois que vous avez configuré vos stratégies de client, déployez le client Skype entreprise, créez 4711,1002 (avril, 2015) ou version ultérieure.
  
Pour plus d’informations sur la configuration de l’utilisation du client avec Skype entreprise Online, notamment la façon de contrôler l’utilisation de la première exécution et les scripts PowerShell que vous pouvez utiliser pour configurer votre environnement, voir [basculement entre les interfaces utilisateur des clients Skype entreprise et Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux à la mise à jour
<a name="support"> </a>

Pour permettre à vous et à votre organisation de se préparer plus facilement à la transition, de nombreuses ressources supplémentaires sont disponibles pour vous aider à planifier, éduquer et engager des utilisateurs finaux.
  
- [Vidéo : présentation de Skype entreprise](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guides de démarrage rapide Skype entreprise (téléchargement)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync devient Skype entreprise-nouveautés.](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype entreprise : Guide détaillé pour les nouveaux utilisateurs](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Pourquoi vois-je Skype entreprise alors que j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

