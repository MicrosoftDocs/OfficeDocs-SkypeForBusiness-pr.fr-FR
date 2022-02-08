---
title: Planifier l’expérience Skype Entreprise client 2015 pour vos utilisateurs
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Résumé : Découvrez la nouvelle Skype Entreprise et les étapes à suivre pour préparer votre environnement et vos utilisateurs à la mise à jour, que vous utilisiez Skype Entreprise Online, Skype Entreprise Server 2019, Skype Entreprise Server  2015, Lync Server 2013 ou Lync Server 2010.'
ms.openlocfilehash: fd3771b351f89210f4757dc97084d85933867050
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395086"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planifier l’expérience Skype Entreprise client 2015 pour vos utilisateurs
 
**Résumé :** Découvrez la nouvelle Skype Entreprise et les étapes à suivre pour préparer votre environnement et vos utilisateurs à la mise à jour, que vous utilisiez Skype Entreprise Online, Skype Entreprise Server 2019, Skype Entreprise Server 2015, Lync Server 2013 ou Lync Server 2010.
  
La mise à jour Office Lync 2013 du 14 avril 2015 inclut la nouvelle interface Skype Entreprise utilisateur. Cette mise à jour permet aux administrateurs de contrôler l’apparence du client et de choisir s’il faut conserver l’expérience client Lync 2013 ou utiliser l’expérience Skype Entreprise client améliorée. Le client Skype Entreprise a effectivement remplacé le client Lync 2013 et a ajouté la possibilité aux administrateurs de choisir entre l’expérience client Lync existante et la nouvelle expérience client Skype Entreprise client. Pour plus d’informations sur cette mise à jour, voir mise à jour du [14 avril 2015 pour Lync 2013 (Skype Entreprise) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Le 12 mai 2015, une autre mise à jour mensuelle de Office inclut le client Skype Entreprise mis à jour. De nombreux clients qui n’ont pas appliqué la mise à jour d’avril choisiront la mise à jour du 12 mai Office 2013. Les informations de cette rubrique vous aideront à préparer votre organisation, votre environnement et vos utilisateurs pour la mise à jour du client. Pour faciliter la transition pour vos utilisateurs et les équipes de support, utilisez les informations de cette rubrique pour vous aider à déterminer l’expérience client que vous souhaitez pour vos utilisateurs, puis a apporté les modifications à votre environnement avant de déployer la mise à jour du client dans votre organisation.
  
- [Quelle expérience client souhaitez-vous pour vos utilisateurs ?](user-experience.md#clientexperience)
    
- [Préparer votre environnement pour le client Skype Entreprise client](user-experience.md#usinglync)
    
- [Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux pour la mise à jour](user-experience.md#support)
    
> [!NOTE]
> L’expérience client Lync 2013 n’est pas une option pour les versions Skype Entreprise client 2016. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez sa version pour vous assurer qu’elle ne commence pas par le numéro 16 . par exemple : 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quelle expérience client souhaitez-vous pour vos utilisateurs ?
<a name="clientexperience"> </a>

Avec le nouveau client Skype Entreprise client, vous pouvez contrôler l’expérience client que vos utilisateurs obtiennent, soit Lync, soit Skype Entreprise. L’expérience client par défaut varie selon que vous utilisez Lync ou Skype Entreprise local ou en ligne. Si vous utilisez Skype Entreprise Online (Lync Online) aujourd’hui avec Applications Microsoft 365 pour les grandes entreprises, Microsoft 365 Business Standard ou Office 2013, la mise à jour Skype Entreprise l’expérience client, qui s’inspire de l’apparence de Skype, sera l’expérience utilisateur par défaut. Si vous utilisez Lync Server en local aujourd’hui, l’expérience client Lync sera la valeur par défaut.
  
Vous pouvez configurer l’expérience client que vos utilisateurs obtiennent à l’aide de stratégies client. Une stratégie de client est un ensemble de paramètres de configuration qui sont appliqués aux utilisateurs lorsqu’ils se connectent à Lync ou à Skype Entreprise.
  
### <a name="skype-for-business-client-experience"></a>Skype Entreprise client

En plus de toutes les fonctionnalités de Lync, Skype Entreprise offre de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières de Skype. Certaines nouvelles fonctionnalités de Skype Entreprise sont disponibles uniquement avec la nouvelle expérience Skype Entreprise client. Pour en savoir plus sur les nouvelles fonctionnalités de Skype Entreprise, voir [Découvrir Skype Entreprise](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Expérience client Lync

L’expérience client Lync est très similaire à l’expérience client Lync 2013 que vos utilisateurs connaissent déjà, mais il existe quelques modifications que vous souhaiterez faire connaître à vos utilisateurs. Pour voir ce qui est différent entre l’expérience client Lync et le client Lync 2013, voir Pourquoi puis-je voir [Skype Entreprise lorsque j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkId=544712) et les liens supplémentaires plus loin dans cette rubrique.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Préparer votre environnement pour le client Skype Entreprise client
<a name="usinglync"> </a>

Vous devez faire certaines choses pour préparer votre environnement à la mise à jour du client. Avant de commencer à apporter des modifications pour configurer l’expérience client, vous devez d’abord vous assurer que vous utilisez une version de Skype Entreprise Server ou de Lync Server qui prend en charge les paramètres de stratégie client.
  
Une fois que vous avez confirmé que vous utilisez une version de Skype Entreprise Server ou de Lync Server qui prend en charge les paramètres de stratégie pour contrôler l’expérience client, vous devez configurer les paramètres de stratégie dans votre environnement. Les étapes spécifiques que vous devez suivre dépendent de la version de Skype Entreprise Server ou de Lync Server que vous utilisez, et selon que vos utilisateurs sont locaux ou en ligne. 
  
Vous devez apporter ces modifications avant la livraison de la mise à jour du client à vos utilisateurs afin de pouvoir contrôler l’expérience client à partir du premier démarrage du client Skype Entreprise client. Les tableaux suivants vous indiquent les étapes à suivre pour configurer votre environnement pour l’expérience client souhaitée pour vos utilisateurs.
  
|**Déploiement**|**Skype Entreprise client**|**Expérience client Lync**|
|:-----|:-----|:-----|
|Skype Entreprise Online  <br/> |Il n’existe aucune autre étape que le déploiement du client build 4711.1002 (avril 2015) ou ultérieur.  <br/> |[Utiliser l’expérience client Lync avec Skype Entreprise Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Entreprise Server 2015  <br/> |Il n’existe aucune autre étape que le déploiement du client build 4711.1002 (avril 2015) ou ultérieur.  <br/> |[Utiliser l’expérience client Lync avec Skype Entreprise Server en local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 et Lync Server 2010  <br/> |[Utiliser l Skype client local avec Lync Server 2013 ou Lync Server 2010](user-experience.md#SkypewithLynconprem) <br/> |[Utiliser l’expérience client Lync avec Lync Server 2013 ou Lync Server 2010 en local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utiliser l Skype client local avec Lync Server 2013 ou Lync Server 2010
<a name="SkypewithLynconprem"> </a>

Suivez les étapes de cette section si vous souhaitez configurer l’expérience Skype client dans un déploiement local. Expérience par défaut pour l’local
  
 **Étape 1 :** Tout d’abord, assurez-vous que vous exécutez une version de Lync Server qui prend en charge les paramètres de stratégie client.
  
- **Lync Server 2013** - Vous devez être en cours d’exécution de la mise à jour cumulative de décembre 2014 (5.0.8308.857) pour Lync Server 2013 ou une mise à jour ultérieure. Pour plus d’informations, [voir Mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - Vous devez être en cours d’exécution de la mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010 ou une mise à jour ultérieure. Pour plus d’informations, [voir Mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l Skype client avec le client Skype Entreprise client. Il existe **3 options d’utilisation** d’une stratégie de client pour définir l’expérience client.
  
  **Option 1 :** Définissez l Skype client à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais que les stratégies au niveau de l’utilisateur et du site prévalent sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement pour inclure le paramètre pour activer l’expérience Skype client. Cela vous permet d’affecter l’expérience Skype client uniquement aux utilisateurs pour qui la stratégie existante est affectée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3 :** Créez une stratégie à affecter aux utilisateurs qui inclut le paramètre pour l’expérience Skype client. Tout d’abord, créez la stratégie de client et fournissez le nom de la stratégie comme valeur du **paramètre Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Affectez ensuite la stratégie aux utilisateurs, en utilisant le nom de la stratégie (la valeur que vous avez utilisée pour le paramètre **Identity** ) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Étape 3 :** Après avoir configuré vos stratégies client, déployez le client Skype Entreprise, build 4711.1002 (avril 2015) ou ultérieur.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utiliser l’expérience client Lync avec Lync Server 2013 ou Lync Server 2010 en local
<a name="LyncwithLynconprem"> </a>

Il s’agit de l’expérience par défaut lorsque Skype Entreprise client est déployé dans un déploiement Lync Server local. Vous n’avez pas besoin de configurer de stratégies client pour utiliser l’expérience client Lync, mais vous pouvez contrôler le comportement de première utilisation du client. Par défaut, la première fois que les utilisateurs démarrent le client Skype Entreprise, l’expérience client Skype est utilisée et une notification s’affiche aux utilisateurs qui leur demande de redémarrer le client pour obtenir l’expérience client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche la première fois que les utilisateurs démarrent le client, ainsi que désactiver le didacticiel client en modifiant le Registre système sur les ordinateurs clients. Pour les étapes à suivre avant de déployer le client Skype Entreprise, consultez l’une des rubriques suivantes :
  
- **Lync Server 2013**, voir Configurer l’expérience [client avec Skype Entreprise dans Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010** see [Configure the client experience with Skype Entreprise in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utiliser l’expérience client Lync avec Skype Entreprise Server en local
<a name="LyncwithSfBServer"> </a>

Suivez les étapes de cette section si vous souhaitez configurer l’expérience client Lync dans un déploiement Skype Entreprise Server local.
  
Suivez les étapes de cette section si vous souhaitez configurer l’expérience Skype client dans un déploiement local. Expérience par défaut pour l’local
  
 **Étape 1 :** Tout d’abord, déployez Skype Entreprise Server.
  
 **Étape 2 :** Ensuite, utilisez une stratégie de client pour définir l’expérience client Lync avec le client Skype Entreprise client. Il existe **3 options d’utilisation** d’une stratégie de client pour définir l’expérience client.
  
 **Option 1 :** Définissez l’expérience client Lync à l’aide d’une stratégie globale. Notez que la stratégie globale s’applique à tous les utilisateurs de votre déploiement, mais que les stratégies au niveau de l’utilisateur et du site prévalent sur la stratégie globale :
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement pour inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs pour qui la stratégie existante est affectée :
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3 :** Créez une stratégie à affecter aux utilisateurs qui inclut le paramètre pour l’expérience client Lync. Tout d’abord, créez la stratégie de client et fournissez le nom de la stratégie comme valeur du **paramètre Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Affectez ensuite la stratégie aux utilisateurs, en utilisant le nom de la stratégie (la valeur que vous avez utilisée pour le paramètre **Identity** ) comme valeur du paramètre **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 Étape **3** : Facultatif : par défaut, la première fois que les utilisateurs démarrent le client Skype Entreprise, l’expérience client Skype est utilisée et une notification s’affiche pour les utilisateurs leur demandant de redémarrer le client pour obtenir l’expérience client Lync. Vous pouvez configurer votre environnement de sorte que l’expérience client Lync s’affiche la première fois que les utilisateurs démarrent le client, ainsi que désactiver le didacticiel client, en modifiant le Registre système sur les ordinateurs clients. Pour connaître les étapes à suivre avant de déployer le client Skype Entreprise consultez Configurer l’expérience [client avec Skype Entreprise](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Étape 4 :** Après avoir configuré vos stratégies client, déployez le client Skype Entreprise, build 4711.1002 (avril 2015) ou ultérieur.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utiliser l’expérience client Lync avec Skype Entreprise Online
<a name="LyncwithSfBO"> </a>

Si vous souhaitez configurer l’expérience client Lync et utiliser Skype Entreprise Online, suivez les étapes de cette section.
  
Si vous utilisez Skype Entreprise Online, vous pouvez toujours utiliser l’expérience client Lync avec le client Skype Entreprise de votre organisation à l’aide de Remote PowerShell pour configurer des stratégies client. Il existe **3 options d’utilisation** d’une stratégie de client pour définir l’expérience client. Notez que les noms de stratégie et de paramètre sont différents des paramètres que vous utilisez pour configurer l’expérience client lorsque vous utilisez Skype Entreprise ou Lync Server local.
  
 **Option 1 :** Définissez l’expérience client Lync à l’aide d’une stratégie globale. Notez que les stratégies de site et de client appliquées aux utilisateurs seront prioritaires sur une stratégie globale.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2 :** Modifiez une stratégie de client existante que vous utilisez dans votre environnement pour inclure le paramètre permettant d’activer l’expérience client Lync. Cela vous permet d’affecter l’expérience client Lync uniquement aux utilisateurs pour qui la stratégie existante est affectée :
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3 :** Utilisez une instance de stratégie personnalisée qui inclut le paramètre pour l’expérience client Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Après avoir configuré vos stratégies client, déployez le client Skype Entreprise, build 4711.1002 (avril 2015) ou ultérieur.
  
Pour plus d’informations sur la configuration de l’expérience client avec Skype Entreprise Online, notamment la procédure de contrôle de l’expérience de première utilisation et les scripts PowerShell que vous pouvez utiliser pour configurer votre environnement, voir Basculement entre les [interfaces utilisateur du client Skype Entreprise et Lync](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressources pour vous aider à préparer vos équipes de support et vos utilisateurs finaux pour la mise à jour
<a name="support"> </a>

Pour faciliter la préparation de la transition pour vous et votre organisation, de nombreuses ressources supplémentaires sont disponibles pour vous aider à planifier, former et impliquer les utilisateurs finaux.
  
- [Vidéo : Présentation de Skype Entreprise](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype Entreprise guides de démarrage rapide (téléchargement)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync est désormais Skype Entreprise : découvrez les nouveautés](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype Entreprise : guide pas à pas pour les nouveaux utilisateurs](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Pourquoi puis-je voir Skype Entreprise lorsque j’utilise Lync ?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
