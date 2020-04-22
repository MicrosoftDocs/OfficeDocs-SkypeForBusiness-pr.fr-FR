---
title: Planification de l’expérience client Skype entreprise 2015 pour vos utilisateurs
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
description: 'Résumé : Découvrez le nouveau Skype entreprise et les étapes que vous pouvez suivre pour préparer votre environnement et vos utilisateurs à la mise à jour, que vous utilisiez Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015, Lync Server 2013 ou Lync Server 2010.'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777749"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planification de l’expérience client Skype entreprise 2015 pour vos utilisateurs
 
**Résumé :** Découvrez le nouveau Skype entreprise et les étapes que vous pouvez suivre pour préparer votre environnement et vos utilisateurs à la mise à jour, que vous utilisiez Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015, Lync Server 2013 ou Lync Server 2010.
  
Le 14 avril 2015 Office Update pour Lync 2013 inclut la nouvelle interface utilisateur Skype entreprise. Cette mise à jour permet aux administrateurs de contrôler l’apparence du client et de conserver l’expérience client Lync 2013 ou d’utiliser l’expérience client Skype entreprise améliorée. Le client Skype entreprise a effectivement remplacé le client Lync 2013 et a ajouté la possibilité aux administrateurs de choisir entre l’expérience client Lync existante et la nouvelle expérience client Skype entreprise. Pour plus d’informations sur cette mise à jour, voir la [mise à jour du 2015 14 avril KB2889923 pour Lync 2013 (Skype entreprise) ()](https://support.microsoft.com/kb/2889923/).
  
Le 12 mai, 2015 il y aura une autre mise à jour mensuelle d’Office incluant le client Skype entreprise mis à jour. De nombreux clients qui n’ont pas appliqué la mise à jour d’avril reprendront la mise à jour de mai 12 pour Office 2013. Les informations contenues dans cette rubrique vous aideront à préparer votre organisation, votre environnement et vos utilisateurs pour la mise à jour du client. Pour faciliter la transition pour vos utilisateurs et équipes de support technique, utilisez les informations de cette rubrique pour vous aider à déterminer l’expérience client souhaitée pour vos utilisateurs, puis à effectuer les modifications dans votre environnement avant de déployer la mise à jour du client dans votre organisation.
  
- [Quelle expérience client souhaitez-vous pour vos utilisateurs ?](user-experience.md#clientexperience)
    
- [Préparation de votre environnement pour le client Skype entreprise](user-experience.md#usinglync)
    
- [Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux à la mise à jour](user-experience.md#support)
    
> [!NOTE]
> L’expérience client Lync 2013 n’est pas une option pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client Lync 2013, vérifiez la version du client pour vous assurer qu’elle ne commence pas par le numéro 16 ; par exemple : 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quelle expérience client souhaitez-vous pour vos utilisateurs ?
<a name="clientexperience"> </a>

Avec le nouveau client Skype entreprise, vous pouvez contrôler l’expérience client que vos utilisateurs peuvent obtenir, Lync ou Skype entreprise. L’expérience client par défaut varie selon que vous utilisez Lync ou Skype entreprise en local ou en ligne. Si vous utilisez Skype entreprise Online (Lync Online) aujourd’hui avec les applications Microsoft 365 pour entreprise, Microsoft 365 Business standard ou Office 2013, l’expérience client Skype entreprise mise à jour (inspirée par l’apparence de Skype) sera l’expérience utilisateur par défaut. Si vous utilisez Lync Server en local dès aujourd’hui, l’expérience client Lync sera la valeur par défaut.
  
Vous pouvez configurer l’expérience client que vos utilisateurs peuvent obtenir en utilisant des stratégies client. Une stratégie client est un ensemble de paramètres de configuration qui sont appliqués aux utilisateurs lorsqu’ils se connectent à Lync ou Skype entreprise.
  
### <a name="skype-for-business-client-experience"></a>Expérience client Skype entreprise

En plus de toutes les fonctionnalités de Lync, Skype entreprise offre de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières de Skype. Certaines nouvelles fonctionnalités de Skype entreprise sont disponibles uniquement avec la nouvelle expérience client Skype entreprise. Pour en savoir plus sur les nouvelles fonctionnalités de Skype entreprise, reportez-vous à la rubrique [découvrir Skype entreprise](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Expérience client Lync

L’expérience client Lync est très semblable à l’expérience client Lync 2013 que vos utilisateurs connaissent déjà, mais il y a quelques modifications que vous souhaiteriez que vos utilisateurs connaissent. Pour voir les différences entre l’expérience client Lync et le client Lync 2013, voir pourquoi est-ce que [je vois Skype entreprise lorsque j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkId=544712) et les liens supplémentaires plus loin dans cette rubrique.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Préparation de votre environnement pour le client Skype entreprise
<a name="usinglync"> </a>

Vous devrez effectuer quelques opérations pour préparer votre environnement à la mise à jour du client. Avant d’apporter des modifications à la configuration de l’expérience client, vous devez d’abord vous assurer que vous utilisez une version de Skype entreprise Server ou Lync Server qui prend en charge les paramètres de stratégie client.
  
Une fois que vous avez confirmé que vous utilisez une version de Skype entreprise Server ou Lync Server qui prend en charge les paramètres de stratégie pour contrôler l’expérience client, vous devez configurer les paramètres de stratégie dans votre environnement. Les étapes spécifiques que vous devez suivre dépendent de la version de Skype entreprise Server ou de Lync Server que vous utilisez, et si vos utilisateurs sont en local ou en ligne. 
  
Ces modifications doivent être apportées avant que la mise à jour du client soit remise à vos utilisateurs afin que vous puissiez contrôler l’expérience client à la première ouverture du client Skype entreprise. Le tableau suivant vous indique les étapes à suivre pour configurer votre environnement pour l’expérience client souhaitée pour vos utilisateurs.
  
|**Déploiement**|**Expérience client Skype entreprise**|**Expérience client Lync**|
|:-----|:-----|:-----|
|Skype Entreprise Online  <br/> |Il n’existe pas d’autres étapes que le déploiement de la version cliente 4711,1002 (avril 2015) ou une version ultérieure.  <br/> |[Utilisation de l’expérience client Lync avec Skype entreprise Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Entreprise Server 2015  <br/> |Il n’existe pas d’autres étapes que le déploiement de la version cliente 4711,1002 (avril 2015) ou une version ultérieure.  <br/> |[Utilisation de l’expérience client Lync avec Skype entreprise Server en local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 et Lync Server 2010  <br/> |[Utilisation de l’expérience client Skype avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#SkypewithLynconprem) <br/> |[Utilisation de l’expérience client Lync avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilisation de l’expérience client Skype avec Lync Server 2013 ou Lync Server 2010 en local
<a name="SkypewithLynconprem"> </a>

Suivez les étapes décrites dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut pour les locaux
  
 **Étape 1 :** Tout d’abord, assurez-vous que vous exécutez une version de Lync Server qui prend en charge les paramètres de stratégie client.
  
- **Lync server 2013** -vous devez exécuter la mise à jour cumulative de décembre 2014 (5.0.8308.857) pour Lync Server 2013 ou une mise à jour ultérieure. Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** -vous devez exécuter la mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010 ou une mise à jour ultérieure. Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience client Skype avec le client Skype entreprise. Il existe **trois options** pour l’utilisation d’une stratégie client pour définir l’expérience client.
  
  **Option 1 :** Définir l’expérience client Skype à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais que les stratégies utilisateur et de niveau site prévalent sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement afin d’inclure le paramètre permettant d’activer l’expérience client Skype. Cela vous permet d’affecter l’expérience client Skype uniquement aux utilisateurs auxquels la stratégie existante est attribuée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3 :** Créer une stratégie à attribuer aux utilisateurs qui incluent le paramètre pour l’expérience client Skype. Tout d’abord, créez la nouvelle stratégie client et indiquez le nom de la stratégie en tant que valeur du paramètre **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Ensuite, affectez la stratégie à des utilisateurs en utilisant le nom de la stratégie (la valeur que vous avez utilisée pour le paramètre **Identity** ) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Étape 3 :** Une fois que vous avez configuré vos stratégies client, déployez le client Skype entreprise, Build 4711,1002 (avril 2015) ou une version ultérieure.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilisation de l’expérience client Lync avec Lync Server 2013 ou Lync Server 2010 en local
<a name="LyncwithLynconprem"> </a>

Il s’agit de l’expérience par défaut lorsque le client Skype entreprise est déployé dans un déploiement Lync Server local. Vous n’avez pas besoin de configurer des stratégies client pour utiliser l’expérience client Lync, mais vous pouvez contrôler le comportement de la première exécution pour le client. Par défaut, la première fois que les utilisateurs démarrent le client Skype entreprise, l’expérience client Skype est utilisée et une notification s’affiche pour les utilisateurs qui les demandent à redémarrer le client pour obtenir l’expérience client Lync. Vous pouvez configurer votre environnement afin que l’expérience client Lync soit affichée la première fois que les utilisateurs démarrent le client, ainsi que désactiver le didacticiel client en modifiant le registre système sur les ordinateurs clients. Pour connaître les étapes à suivre avant de déployer le client Skype entreprise, consultez l’une des rubriques suivantes :
  
- **Lync server 2013**, reportez-vous à [la rubrique Configure the client expérience with Skype for Business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** voir [configure the client expérience with Skype for Business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utilisation de l’expérience client Lync avec Skype entreprise Server en local
<a name="LyncwithSfBServer"> </a>

Suivez les étapes décrites dans cette section si vous voulez configurer l’expérience client Lync dans un déploiement Skype entreprise Server sur site.
  
Suivez les étapes décrites dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut pour les locaux
  
 **Étape 1 :** Tout d’abord, déployez Skype entreprise Server.
  
 **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience client Lync avec le client Skype entreprise. Il existe **trois options** pour l’utilisation d’une stratégie client pour définir l’expérience client.
  
 **Option 1 :** Définir l’expérience client Lync à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais que les stratégies utilisateur et de niveau site prévalent sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement afin d’inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience du client Lync uniquement aux utilisateurs auxquels la stratégie existante est attribuée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3 :** Créer une stratégie à attribuer aux utilisateurs qui incluent le paramètre pour l’expérience client Lync. Tout d’abord, créez la nouvelle stratégie client et indiquez le nom de la stratégie en tant que valeur du paramètre **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Ensuite, affectez la stratégie à des utilisateurs en utilisant le nom de la stratégie (la valeur que vous avez utilisée pour le paramètre **Identity** ) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Étape 3 : facultatif :** par défaut, la première fois que les utilisateurs démarrent le client Skype entreprise, l’expérience client Skype est utilisée et une notification s’affiche pour inviter les utilisateurs à redémarrer le client pour obtenir l’expérience client Lync. Vous pouvez configurer votre environnement afin que l’expérience client Lync soit affichée la première fois que les utilisateurs démarrent le client, ainsi que désactiver le didacticiel client, en modifiant le registre système sur les ordinateurs clients. Pour connaître les étapes à suivre avant de déployer le client Skype entreprise, consultez [la rubrique Configure the client expérience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Étape 4 :** Une fois que vous avez configuré vos stratégies client, déployez le client Skype entreprise, Build 4711,1002 (avril 2015) ou une version ultérieure.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utilisation de l’expérience client Lync avec Skype entreprise Online
<a name="LyncwithSfBO"> </a>

Suivez les étapes décrites dans cette section si vous voulez configurer l’expérience client Lync et que vous utilisez Skype entreprise online.
  
Si vous utilisez Skype entreprise Online, vous pouvez toujours utiliser l’expérience client Lync avec le client Skype entreprise dans votre organisation à l’aide de PowerShell à distance pour configurer les stratégies client. Il existe **trois options** pour l’utilisation d’une stratégie client pour définir l’expérience client. Notez que les noms de stratégie et de paramètre diffèrent de ceux que vous utilisez pour configurer l’expérience client lorsque vous utilisez Skype entreprise ou Lync Server en local.
  
 **Option 1 :** Définir l’expérience client Lync à l’aide d’une stratégie globale. Notez que les stratégies de client et de site appliquées aux utilisateurs seront prioritaires sur une stratégie globale.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement afin d’inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience du client Lync uniquement aux utilisateurs auxquels la stratégie existante est attribuée :
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3 :** Utilisez une instance de stratégie personnalisée qui inclut le paramètre pour l’expérience client Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Une fois que vous avez configuré vos stratégies client, déployez le client Skype entreprise, Build 4711,1002 (avril 2015) ou une version ultérieure.
  
Pour plus d’informations sur la configuration de l’expérience client avec Skype entreprise Online, y compris la procédure de contrôle de l’expérience de première exécution et des scripts PowerShell que vous pouvez utiliser pour configurer votre environnement, voir [basculement entre les interfaces utilisateur des clients Skype entreprise et Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux à la mise à jour
<a name="support"> </a>

Pour faciliter la préparation de la transition pour vous et votre organisation, nous disposons de nombreuses ressources supplémentaires pour vous aider à planifier, éduquer et engager des utilisateurs finaux.
  
- [Vidéo : présentation de Skype entreprise](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guides de démarrage rapide Skype entreprise (téléchargement)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync est désormais Skype entreprise, voir what’s New](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype entreprise : Guide pas à pas pour les nouveaux utilisateurs](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Pourquoi Skype entreprise s’affiche-t-il lorsque j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

