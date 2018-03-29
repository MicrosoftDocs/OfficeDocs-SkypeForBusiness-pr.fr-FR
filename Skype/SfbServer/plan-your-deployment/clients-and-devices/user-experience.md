---
title: Planification de l’expérience client de Skype Entreprise pour vos utilisateurs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Résumé : Découvrez le nouveau Skype pour les entreprises et les étapes à que suivre pour préparer votre environnement et à vos utilisateurs pour la mise à jour, si vous utilisez Skype pour Business Online, Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.'
ms.openlocfilehash: 6ab79741a7a536e80beda0bc529351741136ea13
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a>Planification de l’expérience client de Skype Entreprise pour vos utilisateurs
 
**Résumé :** Découvrez le nouveau Skype pour les entreprises et les étapes à que suivre pour préparer votre environnement et à vos utilisateurs pour la mise à jour, si vous utilisez Skype pour Business Online, Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.
  
Le 14 avril 2015 mise à jour d’Office pour Lync 2013 comprend le nouveau Skype pour interface utilisateur métier. Cette mise à jour permet aux administrateurs de contrôler l’aspect du client et indiquez si vous souhaitez conserver l’expérience du client Lync 2013 ou utiliser le Skype améliorée pour une expérience client. Le Skype pour client d’entreprise remplacé le client Lync 2013 et ajouté la possibilité pour les administrateurs de choisir entre l’expérience du client Lync existant et le nouveau Skype pour une expérience client. Pour plus d’informations sur cette mise à jour, consultez [14 avril 2015, mise à jour pour Lync 2013 (Skype pour les entreprises) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Sur le 12 mai 2015, il y aura une autre mise à jour mensuelle à partir d’Office qui inclut la mise à jour Skype pour client d’entreprise. De nombreux clients qui n’a pas appliqué la mise à jour reprendra le 12 mai avril mise à jour pour Office 2013. Les informations de cette rubrique vous aideront à préparer votre organisation, votre environnement et vos utilisateurs pour la mise à jour du client. Pour faciliter cette transition pour vos utilisateurs et vos équipes de support, utilisez les informations de cette rubrique pour mieux déterminer l’expérience client que vous souhaitez utiliser et apportez les modifications nécessaires à votre environnement avant de déployer la mise à jour du client dans votre organisation.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Préparez votre environnement pour le Skype pour client d’entreprise](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> L’expérience du client Lync 2013 n’est pas une option pour Skype pour les versions clientes de 2016 de l’entreprise. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne démarre pas avec le nombre 16 ; par exemple : 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quelle expérience client voulez-vous pour vos utilisateurs ?
<a name="clientexperience"> </a>

Avec le nouveau Skype pour client d’entreprise, vous pouvez contrôler quel l’expérience client vos utilisateurs obtiennent, Lync ou Skype pour les entreprises. L’expérience du client par défaut varie selon que vous utilisez Lync ou Skype pour professionnels sur site ou en ligne. Si vous utilisez Skype pour Business Online (Lync Online) aujourd'hui avec Office 365 ProPlus, Office 365 Business Premium ou Office 2013, expérience de la mise à jour Skype pour client d’entreprise — inspirés par l’aspect et la convivialité de Skype — sera l’expérience de l’utilisateur par défaut. Si vous utilisez Lync Server sur site dès aujourd'hui, l’expérience du client Lync sera la valeur par défaut.
  
Vous pouvez configurer l’expérience client de vos utilisateurs à l’aide de stratégies client. Une stratégie client est un ensemble de paramètres de configuration qui sont appliqués aux utilisateurs lors de leur connexion à Lync ou Skype pour les entreprises.
  
### <a name="skype-for-business-client-experience"></a>Expérience client Skype Entreprise

En plus de toutes les fonctionnalités de Lync, Skype pour entreprise fournit de nouvelles fonctionnalités avec des commandes plus simples et familiers icônes de Skype. Certaines nouvelles fonctionnalités de Skype pour entreprise ne sont disponibles qu’avec le nouveau Skype pour une expérience client. Pour en savoir plus sur les nouvelles fonctionnalités de Skype pour les entreprises, consultez [Découverte de Skype pour les entreprises](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Expérience client Lync

L’expérience client Lync est très similaire à l’expérience client Lync 2013 que vos utilisateurs connaissent déjà, mais voici quelques modifications que vous voudrez sûrement présenter à vos utilisateurs. Pour voir quelle est la différence entre l’expérience du client Lync et le client Lync 2013, consultez [Pourquoi voir Skype pour entreprise lorsque j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkId=544712) et les liens supplémentaires plus loin dans cette rubrique.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Préparation de votre environnement pour le client Skype Entreprise
<a name="usinglync"> </a>

Pour préparer votre environnement pour la mise à jour du client, vous devez effectuer quelques petites opérations. Avant de commencer à apporter des modifications à la configuration de l’expérience client, vous devez d’abord vous assurer que vous utilisez une version de Skype pour Business Server ou Lync Server prenant en charge les paramètres de stratégie du client.
  
Une fois que vous avez confirmé que vous utilisez une version de Skype pour Lync Server prenant en charge les paramètres de stratégie pour contrôler l’expérience du client ou de Business Server, vous devez configurer les paramètres de stratégie dans votre environnement. Les étapes spécifiques à suivre dépendent de la version de Skype pour Business Server ou de Lync Server que vous utilisez et si vos utilisateurs sont sur site ou en ligne. 
  
Vous voudrez effectuer ces modifications avant la mise à jour du client est remis aux utilisateurs qui vous pouvez de contrôler l’expérience du client à partir de la première fois qu’ils démarrent le Skype pour client d’entreprise. Les tableaux suivants vous indique la marche à suivre pour configurer votre environnement pour l’expérience du client souhaité pour vos utilisateurs.
  
|**Déploiement**|**Skype pour une expérience client**|**Expérience du client Lync**|
|:-----|:-----|:-----|
|Skype Entreprise Online  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utiliser l’expérience du client Lync avec Skype pour professionnels en ligne](user-experience.md#LyncwithSfBO) <br/> |
|Skype Entreprise Server 2015  <br/> |En dehors du déploiement de la version 4711.1002 (avril 2015) ou ultérieure du client, il n’y a pas étape supplémentaire.  <br/> |[Utiliser l’expérience du client Lync avec Skype pour Business Server sur site](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 et Lync Server 2010  <br/> |[L’expérience du client Skype avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#SkypewithLynconprem) <br/> |[L’expérience du client Lync avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>L’expérience du client Skype avec Lync Server 2013 ou Lync Server 2010 en local
<a name="SkypewithLynconprem"> </a>

Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, assurez-vous que vous exécutez une version de Lync Server prenant en charge les paramètres de stratégie du client.
  
- **Lync Server 2013** - vous devez exécuter le 2014 décembre mise à jour Cumulative (5.0.8308.857) de Lync Server 2013 ou une mise à jour ultérieure. Pour plus d’informations, consultez [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - vous devez exécuter le février 2015 mise à jour Cumulative (4.0.7577.710) de Lync Server 2010 ou une mise à jour ultérieure. Pour plus d’informations, consultez [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
 **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience du client Skype avec le Skype pour client d’entreprise. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client.
  
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

 **Étape 3 :** Une fois que vous avez configuré vos stratégies client, déployer le Skype pour client entreprise, génération 4711.1002 (avril, 2015) ou une version ultérieure.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>L’expérience du client Lync avec Lync Server 2013 ou Lync Server 2010 en local
<a name="LyncwithLynconprem"> </a>

Il s’agit de l’expérience par défaut lorsque le Skype pour client d’entreprise est déployée dans un déploiement de Lync Server sur site. Vous n’avez pas besoin de configurer des stratégies client pour utiliser l’expérience client Lync, mais vous avez la possibilité de contrôler le comportement lors de la première utilisation du client. Par défaut, les première fois que des utilisateurs démarrent le Skype pour client d’entreprise, l’expérience du client Skype est utilisé et une notification est affichée aux utilisateurs qui demande qu’ils redémarrer le client pour obtenir l’expérience du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client en modifiant le Registre système sur les ordinateurs du client. Pour connaître les étapes que vous devez effectuer avant de déployer le Skype pour client d’entreprise, consultez une des rubriques suivantes :
  
- **Lync Server 2013**, voir la rubrique [Configure le client expérience avec Skype pour entreprise dans Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** voir [configurer le client expérience avec Skype pour entreprise dans Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Server en local
<a name="LyncwithSfBServer"> </a>

Suivez les étapes de cette section si vous souhaitez configurer l’expérience du client Lync dans un Skype sur site pour le déploiement de Business Server 2015.
  
Suivez la procédure décrite dans cette section si vous voulez configurer l’expérience client Skype dans un déploiement local. L’expérience par défaut est le mode en local.
  
 **Étape 1 :** Tout d’abord, déployer Skype pour Business Server 2015.
  
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

 **Étape 3 : facultatif** - par défaut, les première fois que des utilisateurs démarrent le Skype pour client d’entreprise, l’expérience du client Skype est utilisé et une notification est affichée aux utilisateurs leur demandant de redémarrer le client pour obtenir l’expérience du client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche au premier démarrage du client et désactiver le didacticiel du client, en modifiant le Registre système sur les ordinateurs du client. Pour [configurer le client expérience avec Skype pour entreprise](../../deploy/deploy-clients/configure-the-client-experience.md), consultez les étapes que vous devez effectuer avant de déployer le Skype pour client d’entreprise.
  
 **Étape 4 :** Une fois que vous avez configuré vos stratégies client, déployer le Skype pour client entreprise, génération 4711.1002 (avril, 2015) ou une version ultérieure.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utilisation de l’expérience client Lync avec Skype Entreprise Online
<a name="LyncwithSfBO"> </a>

Suivez les étapes de cette section si vous souhaitez configurer l’expérience du client Lync et vous utilisez Skype pour l’activité en ligne.
  
Si vous utilisez Skype pour professionnels en ligne, vous pouvez toujours utiliser l’expérience du client Lync avec le Skype pour client d’entreprise de votre organisation à l’aide du PowerShell distant pour configurer des stratégies de client. Il existe **trois options** pour utiliser une stratégie client afin de définir l’expérience client. Notez que les noms de paramètre et de stratégie différents de celui des paramètres que vous utilisez pour configurer l’expérience client, lorsque vous utilisez Skype pour les entreprises ou Lync Server sur site.
  
 **Option 1 :** Définir l’expérience du client Lync à l’aide d’une stratégie globale. Notez que les stratégies de site et du client appliquées aux utilisateurs ont priorité sur une stratégie globale.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2 :** modifiez une stratégie client existante que vous utilisez dans votre environnement afin d’y inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs auxquels la stratégie existante est affectée :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3 :** Utilisez une instance de stratégie personnalisée qui inclut le paramètre pour l’expérience du client Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Une fois que vous avez configuré vos stratégies client, déployer le Skype pour client entreprise, génération 4711.1002 (avril, 2015) ou une version ultérieure.
  
Pour plus d’informations sur la façon de configurer le client expérience avec Skype pour professionnels en ligne, y compris les étapes sur la façon de contrôler la première expérience d’exécution et les scripts PowerShell vous permet de configurer votre environnement, reportez-vous à la section [de commutation entre le Skype pour les entreprises et les interfaces utilisateur du client Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux à la mise à jour
<a name="support"> </a>

Pour faire de votre organisation et préparer la transition, nous disposons de nombreuses ressources supplémentaires disponibles pour vous aider à planifier, à former et à engager les utilisateurs finaux.
  
- [Vidéo : Présentation de Skype pour entreprise](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype pour professionnels des Guides de démarrage rapide (téléchargement)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync est désormais Skype pour entreprises — voir Nouveautés](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype pour les entreprises : guide pas à pas pour les nouveaux utilisateurs](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Pourquoi voir quand j’utilise Lync le Skype pour les entreprises ?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

