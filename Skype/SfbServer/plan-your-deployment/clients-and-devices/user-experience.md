---
title: Planification de l’expérience client de Skype Entreprise pour vos utilisateurs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Résumé : Découvrez le nouveau Skype pour les entreprises et les étapes à que suivre pour préparer votre environnement et vos utilisateurs pour la mise à jour, si vous utilisez Skype pour Business Online, Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.'
ms.openlocfilehash: eaa8b7835cb3834ff9cc24a6dc941b47a2796b9f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a>Planification de l’expérience client de Skype Entreprise pour vos utilisateurs
 
**Résumé :** Découvrez le nouveau Skype pour les entreprises et les étapes à que suivre pour préparer votre environnement et vos utilisateurs pour la mise à jour, si vous utilisez Skype pour Business Online, Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.
  
14 avril 2015 Office mise à jour pour Lync 2013 inclut la nouvelle Skype pour l’interface utilisateur d’entreprise. Cette mise à jour permet aux administrateurs de contrôler l’apparence du client et indiquez si vous souhaitez conserver l’expérience du client Lync 2013 ou utiliser le Skype améliorée pour une expérience client. Le Skype pour client Business remplacé le client Lync 2013 et ajouté la possibilité pour les administrateurs de choisir entre l’expérience du client Lync existant et le nouveau Skype pour une expérience client. Pour plus d’informations sur cette mise à jour, consultez [14 avril 2015, mettre à jour pour Lync 2013 (Skype pour les entreprises) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Sur 12 mai 2015, il y aura une autre mise à jour tous les mois à partir d’Office qui inclut la mise à jour Skype pour client d’entreprise. De nombreux clients qui n’a pas appliqué la mise à jour sera Décrochez le 12 mai avril mise à jour pour Office 2013. Les informations de cette rubrique vous aideront à préparer votre organisation, votre environnement et vos utilisateurs pour la mise à jour du client. Pour faciliter cette transition pour vos utilisateurs et vos équipes de support, utilisez les informations de cette rubrique pour mieux déterminer l’expérience client que vous souhaitez utiliser et apportez les modifications nécessaires à votre environnement avant de déployer la mise à jour du client dans votre organisation.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Préparer votre environnement pour le Skype pour client d’entreprise](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> L’expérience du client Lync 2013 n’est pas une option pour Skype pour les versions clientes de 2016 Business. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro de 16 ; par exemple : 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quelle expérience client voulez-vous pour vos utilisateurs ?
<a name="clientexperience"> </a>

Avec la nouvelle Skype pour client d’entreprise, vous pouvez contrôler l’expérience client obtiennent de vos utilisateurs, Lync ou Skype pour les entreprises. L’expérience du client par défaut varie selon que vous utilisez Lync ou Skype pour Business local ou en ligne. Si vous utilisez Skype pour Business Online (Lync Online) aujourd'hui avec Office 365 ProPlus, Office 365 entreprise Premium ou Office 2013, la mise à jour Skype pour client Business expérience — inspirés par l’aspect de Skype — sera l’expérience utilisateur par défaut. Si vous utilisez Lync Server local aujourd'hui, l’expérience du client Lync sera la valeur par défaut.
  
Vous pouvez configurer l’expérience client de vos utilisateurs à l’aide de stratégies client. Une stratégie de client est un ensemble de paramètres de configuration sont appliquées aux utilisateurs lorsqu’ils se connecter à Lync ou Skype pour les entreprises.
  
### <a name="skype-for-business-client-experience"></a>Expérience client Skype Entreprise

En plus de toutes les fonctionnalités de Lync, Skype pour les entreprises fournit de nouvelles fonctionnalités avec des contrôles simplifiés et icônes familières de Skype. Quelques-unes des nouvelles fonctionnalités dans Skype pour les entreprises sont disponibles uniquement avec la nouvelle Skype pour une expérience client. Pour en savoir plus sur les nouvelles fonctionnalités de Skype pour les entreprises, voir [Découvrir les Skype pour les entreprises](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Expérience client Lync

L’expérience client Lync est très similaire à l’expérience client Lync 2013 que vos utilisateurs connaissent déjà, mais voici quelques modifications que vous voudrez sûrement présenter à vos utilisateurs. Pour vérifier quelle est la différence entre l’expérience du client Lync et le client Lync 2013, voir [Pourquoi voir Skype pour les entreprises lors de l’utilisation de Lync ?](https://go.microsoft.com/fwlink/p/?LinkId=544712) et les liens supplémentaires plus loin dans cette rubrique.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Préparation de votre environnement pour le client Skype Entreprise
<a name="usinglync"> </a>

Pour préparer votre environnement pour la mise à jour du client, vous devez effectuer quelques petites opérations. Avant de commencer à apporter des modifications apportées à la configuration de l’expérience client, vous devez tout d’abord vous assurer que vous utilisez une version de Skype pour Business Server ou un serveur Lync qui prend en charge les paramètres de stratégie de client.
  
Une fois que vous avez vérifié que vous utilisez une version de Skype pour Business Server ou un serveur Lync qui prend en charge les paramètres de stratégie pour contrôler l’expérience du client, vous devez configurer les paramètres de stratégie dans votre environnement. Les étapes spécifiques, vous devez suivre dépendent de la version de Skype pour Business Server ou de Lync Server que vous utilisez, et si les utilisateurs locaux ou en ligne. 
  
Vous souhaiterez apporter ces modifications avant la mise à jour du client est remis aux utilisateurs qui vous pouvez de contrôler l’expérience du client à partir de la première fois, que lorsqu’ils démarrent la Skype pour client d’entreprise. Les tableaux suivants vous indique les étapes à suivre pour configurer votre environnement pour l’expérience du client de votre choix pour vos utilisateurs.
  
|**Déploiement**|**Skype pour une expérience client**|**Expérience du client Lync**|
|:-----|:-----|:-----|
|Skype Entreprise Online  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utilisez l’expérience du client Lync avec Skype pour Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Entreprise Server 2015  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utilisez l’expérience du client Lync avec Skype pour Business Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 et Lync Server 2010  <br/> |[Utilisez l’expérience du client Skype avec Lync Server 2013 ou de Lync Server 2010 sur site](user-experience.md#SkypewithLynconprem) <br/> |[Utilisez l’expérience du client Lync avec Lync Server 2013 ou de Lync Server 2010 sur site](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilisez l’expérience du client Skype avec Lync Server 2013 ou de Lync Server 2010 sur site
<a name="SkypewithLynconprem"> </a>

Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, assurez-vous que vous exécutez une version de Lync Server qui prend en charge les paramètres de stratégie de client.
  
- **Lync Server 2013** - vous devez exécuter la 2014 décembre mise à jour Cumulative (5.0.8308.857) pour Lync Server 2013 ou une mise à jour ultérieur. Pour plus d’informations, voir [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - vous devez exécuter la février 2015 mise à jour Cumulative (4.0.7577.710) pour Lync Server 2010 ou d’une mise à jour ultérieur. Pour plus d’informations, voir [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
 **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience du client Skype avec la Skype pour client d’entreprise. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client.
  
 **Option 1 :** définissez l’expérience client Skype à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais les stratégies de niveau utilisateur et site ont priorité sur la stratégie globale :
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Skype. Cela vous permet d’affecter l’expérience client Skype uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3 :** créez une stratégie à affecter aux utilisateurs, qui inclut le paramètre de l’expérience client Skype. Commencez par créer la stratégie du client et indiquez le nom de la stratégie sous forme de valeur du paramètre **Identity** :
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Ensuite, affectez la stratégie aux utilisateurs en utilisant le nom de la stratégie (la valeur utilisée pour le paramètre **Identity**) comme valeur du paramètre **PolicyName** :
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Étape 3 :** Une fois que vous avez configuré vos stratégies de client, déployez le Skype pour client Business, version 4711.1002 (avril, 2015) ou version ultérieure.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilisez l’expérience du client Lync avec Lync Server 2013 ou de Lync Server 2010 sur site
<a name="LyncwithLynconprem"> </a>

Il s’agit de l’expérience par défaut lorsque le Skype pour client d’entreprise est déployé dans un déploiement de Lync Server local. Vous n’avez pas besoin de configurer des stratégies client pour utiliser l’expérience client Lync, mais vous avez la possibilité de contrôler le comportement lors de la première utilisation du client. Par défaut, les première fois que les utilisateurs démarrent le Skype pour client d’entreprise, l’expérience du client Skype est utilisé et une notification est affichée aux utilisateurs qui demande qu’ils redémarrez le client pour obtenir de l’expérience du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client en modifiant le Registre système sur les ordinateurs du client. Pour connaître la procédure, vous devez effectuer avant de déployer le Skype pour client d’entreprise, voir une des rubriques suivantes :
  
- **Lync Server 2013**, consultez [configurer le client expérience avec Skype pour l’entreprise dans Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** voir [configurer le client expérience avec Skype pour l’entreprise dans Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Server en local
<a name="LyncwithSfBServer"> </a>

Suivez les étapes décrites dans cette section si vous souhaitez configurer l’expérience du client Lync dans un Skype sur site pour le déploiement de Business Server 2015.
  
Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, déployez Skype pour Business Server 2015.
  
 **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience du client Lync avec le Skype pour client d’entreprise. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client.
  
 **Option 1 :** définissez l’expérience client Lync à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais les stratégies de niveau utilisateur et site ont priorité sur la stratégie globale :
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3 :** créez une stratégie à affecter aux utilisateurs, qui inclut le paramètre de l’expérience client Lync. Commencez par créer la stratégie du client et indiquez le nom de la stratégie sous forme de valeur du paramètre **Identity** :
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Ensuite, affectez la stratégie aux utilisateurs en utilisant le nom de la stratégie (la valeur utilisée pour le paramètre **Identity**) comme valeur du paramètre **PolicyName** :
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Étape 3 : facultatif** - par défaut, les première fois que les utilisateurs démarrent la Skype pour client d’entreprise, l’expérience du client Skype est utilisé et une notification est affichée aux utilisateurs leur demandant de redémarrer le client pour obtenir de l’expérience du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client, en modifiant le Registre système sur les ordinateurs du client. Pour [configurer le client expérience avec Skype pour les entreprises](../../deploy/deploy-clients/configure-the-client-experience.md), consultez les étapes que vous devez effectuer avant de déployer le Skype pour client d’entreprise.
  
 **Étape 4 :** Une fois que vous avez configuré vos stratégies de client, déployez le Skype pour client Business, version 4711.1002 (avril, 2015) ou version ultérieure.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Online
<a name="LyncwithSfBO"> </a>

Suivez les étapes décrites dans cette section si vous souhaitez configurer l’expérience du client Lync et que vous utilisez Skype pour Business Online.
  
Si vous utilisez Skype pour Business Online, vous pouvez toujours utiliser l’expérience du client Lync avec le Skype pour client d’entreprise dans votre organisation à l’aide de PowerShell à distance pour configurer des stratégies de client. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client. Notez que les noms de stratégie et le paramètre diffèrent des paramètres que vous utilisez pour configurer l’expérience du client lorsque vous utilisez Skype pour Lync Server ou de l’entreprise locale.
  
 **Option 1 :** Définir l’expérience du client Lync à l’aide d’une stratégie globale. Notez que les stratégies de site et du client appliqués aux utilisateurs ont priorité sur une stratégie globale.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3 :** Utiliser une instance de stratégie personnalisée qui inclut le paramètre pour l’expérience du client Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Une fois que vous avez configuré vos stratégies de client, déployez le Skype pour client Business, version 4711.1002 (avril, 2015) ou version ultérieure.
  
Pour plus d’informations sur la façon de configurer le client expérience avec Skype pour Business en ligne, y compris les étapes sur la façon de contrôler la première expérience d’exécution et les scripts PowerShell que vous pouvez utiliser pour configurer votre environnement, voir [bascule entre le Skype pour les entreprises et les interfaces utilisateur du client Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux à la mise à jour
<a name="support"> </a>

Pour faire de votre organisation et préparer la transition, nous disposons de nombreuses ressources supplémentaires disponibles pour vous aider à planifier, former et prendre part aux utilisateurs finaux.
  
- [Vidéo : Présentation de Skype pour les entreprises](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype pour les professionnels des Guides de démarrage rapide (télécharger)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync est désormais Skype pour les entreprises, voir Nouveautés](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype pour les entreprises : guide pas à pas pour les nouveaux utilisateurs](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Pourquoi voir Skype pour les entreprises lors de l’utilisation de Lync ?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

