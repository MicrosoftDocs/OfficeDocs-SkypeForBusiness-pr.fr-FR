---
title: Configurer l’expérience client avec Skype Entreprise 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer l’expérience client pour Skype Entreprise utilisateurs.'
ms.openlocfilehash: d1baa06558f7f3dcc4829d1e03c387e9ab54fa32
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845977"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurer l’expérience client avec Skype Entreprise 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’expérience client pour Skype Entreprise 2015.
  
Skype Entreprise 2015 offre une nouvelle expérience utilisateur basée sur l’expérience Skype produit grand public. En plus de toutes les fonctionnalités de Lync, Skype Entreprise offre de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières. Pour plus d’informations sur la nouvelle expérience client, voir [Explorer Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype Entreprise Server prend en charge la nouvelle Skype Entreprise client, ainsi que l’expérience client Lync. En tant qu’administrateur, vous pouvez choisir l’expérience client préférée pour vos utilisateurs. Par exemple, vous pouvez déployer l’expérience client Lync jusqu’à ce que les utilisateurs de votre organisation soient entièrement formés à la nouvelle expérience Skype Entreprise client. Ou, si vous n’avez pas encore mis à niveau tous les utilisateurs vers Skype Entreprise Server, vous souhaitez peut-être que tous les utilisateurs ont la même expérience client jusqu’à ce que tous soient mis à niveau vers le nouveau serveur.
  
> [!IMPORTANT]
> Si votre organisation a déployé Skype Entreprise Server et Lync Server, l’expérience client par défaut varie en fonction des versions du serveur et des paramètres d’interface utilisateur. Lorsque les utilisateurs lancent Skype Entreprise pour la première fois, ils voient toujours l’interface Skype Entreprise utilisateur, même si vous avez sélectionné l’expérience client Lync. Après plusieurs minutes, les utilisateurs sont invités à basculer en mode Lync. Pour plus d’informations, voir **Comportement du client** de premier lancement plus loin dans cette rubrique.
  
> [!NOTE]
> L’expérience client Lync 2013 n’est pas une option pour Skype Entreprise versions clientes 2016 ou ultérieures. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez sa version pour vous assurer qu’elle ne commence pas par le numéro 16 . par exemple : 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurer l’expérience client

Vous pouvez spécifier l’expérience client que les utilisateurs de votre organisation verront à l’aide de l’cmdlet **Set-CSClientPolicy** avec le paramètre EnableSkypeUI :
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

où XdsIdentity fait référence à la stratégie globale ou à une stratégie de site nommée.
  
La commande suivante sélectionne l’expérience client Skype Entreprise pour tous les utilisateurs de votre organisation affectés par la stratégie globale (n’oubliez pas, les stratégies propres au site ou à l’utilisateur remplacent la stratégie globale) : 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

La commande suivante sélectionne l’expérience client Lync pour tous les utilisateurs de votre organisation affectés par la stratégie globale :
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

La commande suivante sélectionne l’expérience Skype Entreprise client pour tous les utilisateurs du site Redmond :
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si vous souhaitez configurer l’expérience client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une stratégie utilisateur à l’aide de l’cmdlet **New-CsClientPolicy,** puis affecter la stratégie à des utilisateurs spécifiques à l’aide de l’cmdlet **Grant-CsClientPolicy.**
  
Par exemple, la commande suivante crée une stratégie de client, SalesClientUI, qui sélectionne l’expérience Skype Entreprise client :
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service Sales :
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportements du client de premier lancement

Par défaut, lorsque les utilisateurs lancent Skype Entreprise 2015 pour la première fois, ils voient toujours l’interface utilisateur Skype Entreprise, même si vous avez sélectionné l’expérience client Lync en paramétant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment. Après plusieurs minutes, les utilisateurs sont invités à basculer en mode Lync.
  
Si vous souhaitez afficher l’interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez ces étapes avant de démarrer pour la première fois après avoir été mis à jour :
  
1. Confirmez que la valeur est définie sur $False la stratégie que vous  `EnableSkypeUI` utilisez, comme décrit précédemment.
    
2. Mettez à jour le Registre système sur l’ordinateur de l’utilisateur. Vous devez le faire avant la première fois que les utilisateurs lancent Skype Entreprise client, et vous ne devez le faire qu’une seule fois. Pour plus d’informations sur la création d’un objet de stratégie de groupe pour mettre à jour le Registre sur un ordinateur joint à un domaine, consultez la section plus loin dans cette rubrique.
    
    Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync],** créez une **valeur** binaire.
    
    Le **nom de la** valeur doit  **être EnableSkypeUI** et les données de la valeur doivent être définies sur **00 00 00 00**.
    
    La clé doit ressembler à ce qui suit :
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

L’interface utilisateur Lync s’affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôler l’affichage du didacticiel sur l’écran d’accueil

Lorsque les utilisateurs ouvrent Skype Entreprise client, le comportement par défaut consiste à afficher un écran d’accueil qui inclut 7 conseils rapides que la plupart des utilisateurs *demandent.* Vous pouvez désactiver l’affichage de l’écran d’accueil tout en permettant aux utilisateurs d’accéder au didacticiel en ajoutant la valeur de Registre suivante sur l’ordinateur client :
  
Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** créez une valeur **DWORD (32 bits).** Le **nom de la** valeur doit être **IsBasicTutorialSeenByUser** et les données de la valeur doivent être définies sur **1**. 
  
La clé doit ressembler à ce qui suit :
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Désactiver le didacticiel client

Si vous ne souhaitez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel client avec la valeur de Registre suivante :
  
Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** créez une valeur **DWORD (32 bits).** Le **nom de la** valeur doit être  **TutorialFeatureEnabled** et les données de la valeur doivent être définies sur **0**.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Vous pouvez activer de nouveau le didacticiel en fixant les données **de la** valeur **sur 1**.
  
## <a name="default-client-behaviors"></a>Comportements des clients par défaut

Si votre organisation a déployé Skype Entreprise Server et Lync Server, l’expérience client varie en fonction des versions du serveur et du Skype’interface utilisateur. Le tableau suivant présente l’expérience client initiale basée sur la version du serveur et le paramètre d’interface utilisateur :
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Expérience client**|
|:-----|:-----|:-----|
|Skype Entreprise Server |Par défaut  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server  |Vrai  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server  |Faux  <br/> |Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise si vous modifiez le paramètre d’interface utilisateur en mode $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)  <br/> |Par défaut  <br/> |Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise si vous modifiez le paramètre d’interface utilisateur en mode $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)  <br/> |Vrai  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)  <br/> |Faux  <br/> |Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise si vous modifiez le paramètre d’interface utilisateur en mode $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Utilisateur invité à basculer en mode Lync (l’utilisateur ne peut pas basculer vers Skype Entreprise ultérieurement)  <br/> |
   
Le tableau suivant illustre l’expérience client lorsque l’administrateur modifie le paramètre initial de l Skype’interface utilisateur :
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Interface utilisateur du client = Lync**|**Interface utilisateur du client = Skype Entreprise**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Server |Vrai  <br/> |Utilisateur invité à basculer vers Skype Entreprise  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server |Faux  <br/> |Mode Lync  <br/> |Utilisateur invité à basculer en mode Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)  <br/> |Vrai  <br/> |Utilisateur invité à basculer vers Skype Entreprise  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)  <br/> |Faux  <br/> |Mode Lync  <br/> |Utilisateur invité à basculer en mode Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Mode Lync (basculement vers Skype Entreprise)  <br/> |Mode Lync (basculement vers Skype Entreprise)  <br/> |
   
Les versions de correctif requises pour gérer la configuration du client Skype Entreprise sont les Skype Entreprise :
  
- Lync Server 2010 - Mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010. Pour plus d’informations, [voir Mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - Mise à jour cumulative de décembre 2014 (5.0.8308.857) pour Lync Server 2013. Pour plus d’informations, [voir Mises à jour pour Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint à un domaine

La mise à jour du Registre pour afficher l’expérience client Lync la première fois qu’un utilisateur lance le client Skype Entreprise 2015 ne doit être effectuée qu’une seule fois. Si vous utilisez un objet de stratégie de groupe (GPO) pour mettre à jour le Registre, vous devez définir l’objet pour créer une valeur au lieu de mettre à jour les données de la valeur. Lorsque l’GPO est appliqué, si la nouvelle valeur n’existe pas, l’objectif de groupe la crée et lui donne la valeur 0. 
  
La procédure suivante décrit comment modifier le Registre afin que l’expérience client Lync s’affiche la première fois qu’un utilisateur lance le client Skype Entreprise 2015. Vous pouvez également utiliser cette procédure pour mettre à jour le Registre afin de désactiver le didacticiel sur l’écran d’accueil comme décrit précédemment.
  
### <a name="to-create-the-gpo"></a>Pour créer l’GPO

1. Démarrez la **console de gestion des stratégies de groupe.**
    
    Pour plus d’informations sur l’utilisation de la Console de gestion des stratégies de groupe, voir La Console de [gestion des stratégies de groupe.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))
    
2. Cliquez avec le bouton droit sur le nœud **Objets de stratégie de** groupe et sélectionnez **Nouveau** dans le menu.
    
3. Dans la boîte de dialogue Nouvel **GPO,** entrez un nom pour l’GPO, par exemple, MakeLyncDefaultUI, puis cliquez sur **OK**.
    
4. Cliquez avec le bouton droit sur le nouvel GPO que vous avez créé, puis sélectionnez **Modifier** dans le menu.
    
5. Dans **l’Éditeur de gestion des** stratégies de groupe, développez **Configuration** utilisateur, développez **Préférences,** **développez Windows Paramètres,** puis sélectionnez le **nœud** du Registre.
    
6. Cliquez avec le bouton droit **sur le** nœud du Registre, puis sélectionnez **Nouvel** élément  >  **de Registre.**
    
7. Dans la **boîte de dialogue Nouvelles propriétés du** Registre, mettez à jour les informations suivantes :
    
   |**Field**|**Valeur à sélectionner ou à entrer**|
   |:-----|:-----|
   |**Action** <br/> |**Créer** <br/> |
   |**Hive** <br/> | HKEY_CURRENT_USER <br/> |
   |**Chemin d’accès de la touche** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nom de la valeur** <br/> |EnableSkypeUI  <br/> |
   |**Type de valeur** <br/> |REG_BINARY  <br/> |
   |**Données de valeur** <br/> |00000000  <br/> |
   
8. Cliquez **sur OK** pour enregistrer vos modifications, puis fermez l’GPO.
    
Ensuite, vous devez lier l’GPO que vous avez créé au groupe d’utilisateurs à qui vous souhaitez affecter la stratégie, tel qu’une ou plusieurs.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Pour utiliser l’GPO pour affecter la stratégie

1. Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l’ou à qui vous souhaitez affecter la stratégie, puis sélectionnez Lien vers un **GPO existant.**
    
2. Dans la boîte de dialogue Sélectionner **un GPO,** sélectionnez l’GPO que vous avez créé, puis **sélectionnez OK.**
    
3. Sur l’ordinateur de l’utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :
       
   ```console
   pupdate /target:user
   ```
     Le message « Mise à jour de la stratégie... » s’affiche pendant l’application de l’objectif de groupe. Une fois terminé, le message « La mise à jour de la stratégie utilisateur s’est terminée correctement » s’affiche.
    
4. Depuis l'invite de commandes, entrez la commande suivante :
    
    **gpresult /r**
    
    Vous devez voir « Objets de stratégie de groupe affectés » avec le nom de l’objet de stratégie de groupe que vous avez créé, affiché ci-dessous.
    
Vous pouvez également vérifier que l’GPO a correctement mis à jour le Registre sur l’ordinateur d’un utilisateur en examinant le Registre. Ouvrez l’Éditeur du Registre et accédez à la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].** Si l’GPO a correctement mis à jour le Registre, vous verrez une valeur nommée EnableSkypeUI avec la valeur 0.
