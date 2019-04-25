---
title: Basculement entre les interfaces utilisateur des clients Skype Entreprise et Lync
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: f248da01bb7046174fd241ed01ad6c0c93111cd9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237998"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Basculement entre les interfaces utilisateur des clients Skype Entreprise et Lync

Dans les organisations utilisant Skype Entreprise Online, vous pouvez utiliser une session PowerShell distante dans Office 365 pour permettre aux utilisateurs de Skype Entreprise d'utiliser le client Skype Entreprise ou l'interface utilisateur du client Skype Entreprise (Lync). Par défaut, l'interface utilisateur du client Skype Entreprise est utilisée. Si vous préférez utiliser l’expérience du client Lync, vous pouvez gérer le comportement du client premier lancement afin d’afficher l’interface utilisateur de Lync en suivant les étapes décrites plus loin dans cette rubrique.
  
> [!NOTE]
> L'expérience client Lync 2013 n'est pas une option pour les versions client de Skype Entreprise 2016. Avant de tenter de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu'elle ne commence pas par le numéro 16. Par exemple : 16.x.x.x. 
  
> [!TIP]
> Si vous souhaitez changer facilement d'interface utilisateur sans procéder manuellement, reportez-vous au [Centre de téléchargement Microsoft ](https://go.microsoft.com/fwlink/?LinkId=532431) pour obtenir un script PowerShell afin de simplifier cette procédure.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Changement d'interface utilisateur de Skype Entreprise pour les utilisateurs

Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell distante, qui se connecte à Skype Entreprise Online. Ce module pris en charge uniquement sur les ordinateurs 64 bits peut être téléchargé à partir du Centre de téléchargement Microsoft : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Pour plus d'informations, reportez-vous à l'article [Configuration de votre ordinateur pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> Le paramètre de stratégie  _Global_ pour le changement d'interface utilisateur ne s'applique pas à un utilisateur pour lequel une stratégie personnalisée est déjà appliquée. Pour pouvoir modifier l'interface utilisateur, vous devez exécuter les opérations suivantes pour chaque utilisateur qui possède une stratégie personnalisée :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> La stratégie  _ClientPolicyEnableSkypeUI_ remplacera le paramètre de stratégie personnalisée en vigueur pour l'utilisateur.
  
Pour permettre à tous les utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Si vous définissez la stratégie actuelle, vous verrez :
  
![PowerShell : SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Pour permettre à tous les utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes : 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Si vous définissez la stratégie actuelle, vous verrez :
  
![PowerShell : SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Pour permettre à un seul utilisateur de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Si vous définissez la stratégie actuelle, vous verrez :
  
![Skype Entreprise Online - Activer l'IU](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Pour permettre à un seul utilisateur de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Si vous définissez la stratégie actuelle, vous verrez :
  
![Skype Entreprise Online - IU désactivée](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Pour permettre à plusieurs utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Pour permettre à plusieurs utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Pour permettre à un groupe d'utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Pour permettre à un groupe d'utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  Le nom d'utilisateur correspond au nom du compte d'utilisateur auquel la stratégie doit être attribuée. Le nom du compte d'utilisateur peut être entré dans l'un des formats suivants :>  Adresse SIP de l'utilisateur>  Nom d'utilisateur principal (UPN)>  Domaine\\nom d'utilisateur>  Nom complet Active Directory de l'utilisateur
  
[Utilisation de Windows PowerShell pour gérer Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Paramètres de stratégie de Skype Entreprise Online

Ce tableau indique l'expérience utilisateur lorsque la stratégie est d'abord appliquée aux utilisateurs :
  
|**Paramètre de stratégie d'administration**|**Interface utilisateur affichée**|
|:-----|:-----|
|La stratégie n'est pas définie. |L'interface utilisateur restera celle du client Skype Entreprise.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|L'interface utilisateur restera celle du client Skype Entreprise.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|L’utilisateur sera invité à basculer vers le Skype pour l’interface utilisateur du client Business (Lync). Le basculement peut être effectué plus tard.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|L’utilisateur utilise la Skype pour l’interface utilisateur du client entreprise. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|L’utilisateur sera invité à basculer vers le Skype pour l’interface utilisateur du client Business (Lync). Un administrateur peut modifier le paramètre afin de basculer sur l'interface utilisateur du client Skype Entreprise ultérieurement. |
   
Ce tableau indique l'expérience utilisateur une fois la stratégie modifiée :
  
|**Paramètre de stratégie d'administration**|**Interface utilisateur de Skype Entreprise (Lync)**|**Interface utilisateur de Skype Entreprise**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|L’utilisateur sera invité à basculer vers le Skype pour l’interface utilisateur du client Business.  <br/> |L’utilisateur continue à utiliser le Skype pour l’interface utilisateur du client entreprise.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|L’utilisateur continue à utiliser le Skype pour interface métier (Lync).  <br/> |L’utilisateur sera invité à basculer vers le Skype pour l’interface utilisateur du client Business (Lync).  <br/> |
|La stratégie n'est pas définie.  <br/> |Les utilisateurs ne verront jamais le Skype pour l’interface utilisateur du client Business (Lync) si la stratégie n’est pas définie. Ils continueront d'utiliser l'interface utilisateur du client Skype Entreprise.  <br/> |L’utilisateur continue à utiliser le Skype pour l’interface utilisateur du client entreprise.  <br/> |
   
Ce tableau présente toutes les stratégies personnalisées Online disponibles. Il existe de nouvelles stratégies créées afin d'offrir plus de flexibilité aux administrateurs qui souhaitent conserver l'ancienne stratégie personnalisée tout en basculant entre les différents indicateurs EnableSkypeUI. Utilisez les applets de commande ci-dessus pour accorder l'une des stratégies ci-dessous à vos utilisateurs.
  
|**Nom de la stratégie**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |False|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|False|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |False|

   
Pour prendre en main Windows PowerShell, consultez ces rubriques :
  
- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>Comportements client au premier lancement

Par défaut, lorsque les utilisateurs lancer Skype pour les entreprises pour la première fois, il apparaît toujours à la Skype pour l’interface utilisateur d’entreprise : même si vous avez sélectionné l’expérience du client Lync en définissant la stratégie du client sur l’expérience du client Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) comme indiqué précédemment. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.
  
Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :
  
1. Suivez la procédure décrite plus haut dans cette rubrique et confirmez que la stratégie client est définie pour désactiver l'interface utilisateur Skype Entreprise.
    
2. Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.
    
    Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, créez une valeur **Binaire**.
    
    Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.
    
    La clé doit se présenter comme celle-ci :
    
    [HKEY_CURRENT_USER\\logiciel\\Microsoft\\Office\\Lync]
    
    « CanSharePptInCollab » = DWORD : 00000001
    
    « CanShareOneNoteInCollab » = DWORD : 00000001
    
    « CanAppShareInCollab » = DWORD : 00000001
    
    « EnableSkypeUI » = hex : 00, 00, 00, 00
    
L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôler l’affichage du didacticiel de l’écran d’accueil

Lorsque les utilisateurs ouvrent la Skype pour client d’entreprise, le comportement par défaut consiste à afficher l’écran d’accueil qui inclut *la plupart des personnes 7 conseils rapides demandent*. Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :
  
Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, créez une valeur **DWORD (32 bit)**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser** et les **données de valeur** doivent être définies sur **1**.
  
La clé doit se présenter comme celle-ci :
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Désactivation du didacticiel client

Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de registre suivante :
  
Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, créez une valeur **DWORD (32 bit)**. Le **nom de la valeur** doit être **TutorialFeatureEnabled** et les **données de valeur** doivent être définies sur **0**.
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint au domaine

La mise à jour du registre pour afficher l'expérience client Lync la première fois qu'un utilisateur lance le client Skype Entreprise ne doit être effectuée qu'une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0.
  
La procédure ci-dessous décrit comment modifier le registre afin que l'expérience client Lync s'affiche la première fois qu'un utilisateur lance le client Skype Entreprise. Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver l'écran d'accueil du didacticiel, comme indiqué précédemment.
  
 **Pour créer l’objet de stratégie de groupe**
  
1. Démarrez la **Console de gestion des stratégies de groupe**.
    
    Pour plus d'informations sur l'utilisation de la Console de gestion des stratégies de groupe, reportez-vous à l'article [Console de gestion des stratégies de groupe](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Cliquez avec le bouton droit sur le nœud **Objets de stratégie de groupe** et sélectionnez **Nouveau** dans le menu.
    
3. Dans la boîte de dialogue **Nouvel objet GPO**, entrez un nom pour l'objet GPO, par exemple, MakeLyncDefaultUI, puis cliquez sur **OK**.
    
4. Cliquez avec le bouton droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **Modifier** dans le menu.
    
5. Dans **Éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre**.
    
6. Cliquez avec le bouton droit sur le nœud **Registre**, puis sélectionnez **Nouveau** > **Élément Registre**.
    
7. Dans la boîte de dialogue **Nouvelles propriétés de registre**, mettez à jour les champs suivants :
    
|**Champ**|**Valeur à sélectionner ou entrer**|
|:-----|:-----|
|**Action** <br/> |**Créer** <br/> |
|**Ruche** <br/> | HKEY_CURRENT_USER <br/> |
|**Chemin d'accès à la clé** <br/> |Logiciel\\Microsoft\\Office\\Lync  <br/> |
|**Nom de la valeur** <br/> |EnableSkypeUI  <br/> |
|**Type de la valeur** <br/> |REG_BINARY  <br/> |
|**Données de la valeur** <br/> |00000000  <br/> |
   
Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.
    
Ensuite, vous devez lier l'objet GPO créé au groupe d'utilisateurs auquel vous voulez affecter la stratégie, par exemple, une unité d'organisation.
  
 **Pour utiliser la stratégie de groupe pour attribuer la stratégie**
  
1. Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l'unité d'organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.
    
2. Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.
    
3. Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :
    
    **gpupdate /target:user**
    
    Le message « mise à jour la stratégie… » s'affiche pendant l'application de l'objet GPO. Au terme de l'opération, le message « La mise à jour de la stratégie utilisateur s'est terminée sans erreur. » s'affiche.
    
4. Dans l'invite de commandes, tapez la commande suivante :
    
    **gpresult /r**
    
    « Objets de stratégie de groupé affectés » doit s'afficher avec le nom de l'objet GPO créé en-dessous.
    
Vous pouvez également vérifier que l'objet de stratégie de groupe a mis à jour le registre sur l'ordinateur de l'utilisateur en examinant le registre. Ouvrez l'Éditeur du registre et accédez à la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Si l'objet GPO a mis à jour correctement le registre, la valeur nommée EnableSkypeUI s'affiche avec la valeur 0.
  
## <a name="related-topics"></a>Voir aussi
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
