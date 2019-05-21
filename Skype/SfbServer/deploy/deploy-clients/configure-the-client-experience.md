---
title: Configurer l’interface client avec Skype entreprise 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Résumé: cette rubrique vous explique comment configurer l’utilisation du client pour les utilisateurs de Skype entreprise.'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298283"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurer l’interface client avec Skype entreprise 2015
 
**Résumé:** Pour plus d’informations sur la configuration de l’utilisation du client pour les utilisateurs de Skype entreprise 2015, lisez cette rubrique.
  
Skype entreprise 2015 offre une nouvelle interface utilisateur qui repose sur l’utilisation des produits Skype. Outre l’ensemble des fonctionnalités de Lync, Skype entreprise fournit de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières. Pour plus d’informations sur la nouvelle interface client, reportez-vous à la rubrique [découvrir Skype entreprise](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype entreprise Server prend en charge la nouvelle interface client Skype entreprise, ainsi que l’interface du client Lync. En tant qu’administrateur, vous pouvez choisir la meilleure expérience client pour vos utilisateurs. Par exemple, vous souhaiterez peut-être déployer l’interface du client Lync jusqu’à ce que les utilisateurs de votre organisation aient pleinement formé la nouvelle interface Skype entreprise. Ou bien, si vous n’avez pas encore effectué la mise à niveau de tous les utilisateurs vers Skype entreprise Server, vous souhaiterez peut-être que tous les utilisateurs disposent de la même expérimentation sur le nouveau serveur.
  
> [!IMPORTANT]
> Si votre organisation utilise à la fois Skype entreprise Server et Lync Server, l’interface client par défaut varie en fonction des versions de serveur et des paramètres d’interface utilisateur. Lorsque les utilisateurs lancent Skype entreprise pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’interface du client Lync. Après plusieurs minutes, l’utilisateur est invité à basculer vers le mode Lync. Pour plus d’informations, voir **Comportements client au premier lancement** dans la suite de cette rubrique.
  
> [!NOTE]
> L’interface du client 2013 de Lync n’est pas disponible pour les versions clientes d’Skype entreprise 2016 ou ultérieures. Avant de configurer votre environnement client pour qu’il utilise le client 2013 Lync, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro 16; par exemple: 16. x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurer l’expérience client

Vous pouvez spécifier l’expérience client des utilisateurs de votre organisation en utilisant l’applet de commande **Set-CSClientPolicy** avec le paramètre EnableSkypeUI :
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

où XdsIdentity renvoie à la stratégie globale ou à une stratégie de site nommé.
  
La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs de votre organisation concernés par la politique globale (n’oubliez pas que les stratégies de site ou d’utilisateur remplacent la stratégie globale): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

La commande suivante sélectionne l’interface du client Lync pour tous les utilisateurs de votre organisation concernés par la stratégie globale:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs du site de Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si vous voulez configurer l’utilisation du client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie d’utilisateur à l’aide de l’applet **de nouvelle** applet de CsClientPolicy, puis affecter la stratégie à des utilisateurs spécifiques à l’aide de l’applet de passe **CsClientPolicy** applet.
  
Par exemple, la commande suivante crée une nouvelle stratégie client, SalesClientUI, qui sélectionne l’interface du client Skype entreprise:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service commercial :
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportements client au premier lancement

Par défaut, lorsque les utilisateurs lancent Skype entreprise 2015 pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’environnement du client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme décrit dessus. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.
  
Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :
  
1. Vérifiez que la valeur de `EnableSkypeUI` est définie sur $false dans la stratégie que vous utilisez, comme décrit précédemment.
    
2. Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.
    
    Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, créez une nouvelle valeur **Binaire**.
    
    Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.
    
    La clé doit se présenter comme celle-ci :
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôler l’affichage du didacticiel de l’écran d’accueil

Lorsque les utilisateurs ouvrent le client Skype entreprise, le comportement par défaut consiste à afficher un écran d’accueil incluant *7 conseils rapides pour la plupart des personnes*. Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :
  
Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser**, et les **données de valeur** doivent être définies sur **1**.
  
La clé doit ressembler à celle-ci :
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Désactivation du didacticiel client

Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de Registre suivante :
  
Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **TutorialFeatureEnabled**, et les **données de valeur** doivent être définies sur **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.
  
## <a name="default-client-behaviors"></a>Comportements du client par défaut

Si votre organisation utilise à la fois Skype entreprise Server et Lync Server Server, l’environnement client varie en fonction des versions du serveur et du paramètre d’interface utilisateur de Skype. Le tableau ci-dessous montre l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Expérience client**|
|:-----|:-----|:-----|
|Skype entreprise Server |Par défaut  <br/> |Skype Entreprise  <br/> |
|Skype entreprise Server  |True  <br/> |Skype Entreprise  <br/> |
|Skype entreprise Server  |False  <br/> |Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)  <br/> |Par défaut  <br/> |Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)  <br/> |True  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)  <br/> |False  <br/> |Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Utilisateur invité à basculer vers le mode Lync (l’utilisateur ne peut pas basculer vers Skype entreprise plus tard)  <br/> |
   
Le tableau suivant indique l’environnement client lorsque l’administrateur modifie le paramètre initial de l’interface utilisateur de Skype:
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Interface utilisateur du client = Lync**|**UI client = Skype Entreprise**|
|:-----|:-----|:-----|:-----|
|Skype entreprise Server |True  <br/> |Utilisateur invité à basculer sur Skype entreprise  <br/> |Skype Entreprise  <br/> |
|Skype entreprise Server |False  <br/> |Mode Lync  <br/> |Utilisateur invité à basculer vers le mode Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)  <br/> |True  <br/> |Utilisateur invité à basculer sur Skype entreprise  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)  <br/> |False  <br/> |Mode Lync  <br/> |Utilisateur invité à basculer vers le mode Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Mode Lync (possibilité de basculer vers Skype entreprise)  <br/> |Mode Lync (possibilité de basculer vers Skype entreprise)  <br/> |
   
Les versions de correctif requises pour gérer la configuration du client Skype entreprise sont les suivantes:
  
- Mise à jour cumulative de Lync Server 2010-février 2015 (4.0.7577.710) pour Lync Server 2010. Pour plus d’informations, voir [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Mise à jour cumulative de Lync Server 2013-décembre 2014 (5.0.8308.857) pour Lync Server 2013. Pour plus d’informations, consultez [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint au domaine

La mise à jour du Registre pour afficher l’utilisation du client Lync la première fois qu’un utilisateur lance le client Skype entreprise 2015 doit être exécuté une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0. 
  
La procédure suivante vous explique comment modifier le registre de manière à ce que l’interface du client Lync s’affiche la première fois qu’un utilisateur lance le client Skype entreprise 2015. Vous pouvez également utiliser cette procédure de mise à jour du registre pour désactiver le didacticiel de l’écran d’accueil comme décrit précédemment.
  
### <a name="to-create-the-gpo"></a>Pour créer l’objet GPO

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
   |**Chemin d’accès à la clé** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nom de la valeur** <br/> |EnableSkypeUI  <br/> |
   |**Type de la valeur** <br/> |REG_BINARY  <br/> |
   |**Données de la valeur** <br/> |00000000  <br/> |
   
8. Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.
    
Ensuite, vous devez lier l’objet GPO créé au groupe d’utilisateurs auquel vous voulez affecter la stratégie, par exemple Unité d’organisation.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Pour utiliser l’objet GPO pour affecter la stratégie

1. Dans la Console de gestion des stratégies de groupe, effectuez un clic droit sur l’Unité d’organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.
    
2. Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.
    
3. Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. Dans l'invite de commandes, tapez la commande suivante :
    
    **gpresult /r**
    
    Vous devriez voir « Objets de stratégie de groupé affectés » avec le nom de l’objet GPO créé s’afficher en-dessous.
    
Vous pouvez aussi vérifier que l’objet GPO a correctement mis à jour le Registre sur un ordinateur d’utilisateur en examinant le Registre. Ouvrez l’Éditeur du Registre et accédez à la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si l’objet GPO a correctement mis à jour le Registre, vous verrez une valeur nommée EnableSkypeUI avec une valeur 0.
  

