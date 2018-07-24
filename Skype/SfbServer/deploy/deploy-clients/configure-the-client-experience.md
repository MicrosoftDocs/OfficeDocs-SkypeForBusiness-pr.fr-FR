---
title: Configurer l’expérience du client avec Skype pour Business 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’expérience du client pour Skype pour les utilisateurs professionnels.'
ms.openlocfilehash: 18fb67b88673dd2edfe3816d485a8cb05c84f3ae
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018187"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurer l’expérience du client avec Skype pour Business 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer l’expérience du client pour Skype pour les utilisateurs professionnels 2015.
  
Skype pour Business 2015 fournit une nouvelle expérience utilisateur qui est basée sur l’expérience de produit Skype consommateur. En plus de toutes les fonctionnalités de Lync, Skype pour les entreprises fournit de nouvelles fonctionnalités avec des contrôles simplifiés et icônes familières. Pour plus d’informations sur l’expérience du client, voir [Explorer de Skype pour les entreprises](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype pour Business Server prend en charge la nouvelle Skype pour une expérience client ainsi que l’expérience du client Lync. En tant qu’administrateur, vous pouvez choisir la meilleure expérience client pour vos utilisateurs. Par exemple, vous pouvez souhaiter déployer l’expérience du client Lync jusqu'à ce que les utilisateurs de votre organisation sont formés dans le nouveau Skype pour une expérience. Ou, si vous n'avez pas encore mis à niveau tous les utilisateurs Skype pour Business Server, vous pouvez tous les utilisateurs aient la même expérience client jusqu'à ce que toutes les sont mis à niveau vers le nouveau serveur.
  
> [!IMPORTANT]
> Si votre organisation a deux Skype pour Business Server et Lync Server déployé, l’expérience du client par défaut varient selon les versions du serveur et les paramètres de l’interface utilisateur. Lorsque les utilisateurs de lancement Skype pour les entreprises pour la première fois, ils verront toujours le Skype pour l’interface utilisateur d’entreprise : même si vous avez sélectionné l’expérience du client Lync. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync. Pour plus d’informations, voir **Comportements client au premier lancement** dans la suite de cette rubrique.
  
> [!NOTE]
> L’expérience du client Lync 2013 n’est pas une option de Skype pour les versions clientes de 2016 Business ou version ultérieure. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro de 16 ; par exemple : 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurer l’expérience client

Vous pouvez spécifier l’expérience client des utilisateurs de votre organisation en utilisant l’applet de commande **Set-CSClientPolicy** avec le paramètre EnableSkypeUI :
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

où XdsIdentity renvoie à la stratégie globale ou à une stratégie de site nommé.
  
La commande suivante sélectionne le Skype pour une expérience de client d’entreprise pour tous les utilisateurs de votre organisation affectée par la stratégie globale (Souvenez-vous, site ou des stratégies spécifiques à l’utilisateur de la stratégie globale remplacent) : 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

La commande suivante sélectionne l’expérience du client Lync pour tous les utilisateurs de votre organisation affectée par la stratégie globale :
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

La commande suivante sélectionne le Skype pour une expérience de client d’entreprise pour tous les utilisateurs au sein du site de Redmond :
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si vous souhaitez configurer l’expérience du client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie utilisateur à l’aide de l’applet de commande **New-CsClientPolicy** et puis attribuez-les à des utilisateurs spécifiques à l’aide de la **Grant-CsClientPolicy** applet de commande.
  
Par exemple, la commande suivante crée une nouvelle stratégie de client, SalesClientUI, qui sélectionne le Skype pour une expérience client :
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service commercial :
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportements client au premier lancement

Par défaut, lorsque les utilisateurs lancer Skype pour Business 2015 pour la première fois, toujours verront le Skype pour l’interface utilisateur d’entreprise : même si vous avez sélectionné l’expérience du client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme indiqué précédemment. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.
  
Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :
  
1. Vérifiez que la valeur de `EnableSkypeUI` est défini sur $False dans la stratégie que vous utilisez comme décrit précédemment.
    
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
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôle de l'affichage du didacticiel de l'écran d'accueil

Lorsque les utilisateurs ouvrent la Skype pour client d’entreprise, le comportement par défaut consiste à afficher l’écran d’accueil qui inclut *la plupart des personnes 7 conseils rapides demandent*. Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :
  
Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser**, et les **données de valeur** doivent être définies sur **1**.
  
La clé doit se présenter comme celle-ci :
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Désactivation du didacticiel client

Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de registre suivante :
  
Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **TutorialFeatureEnabled**, et les **données de valeur** doivent être définies sur **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.
  
## <a name="default-client-behaviors"></a>Comportements du client par défaut

Si votre organisation a deux Skype pour Business Server et Lync Server déployé, l’expérience du client varient en fonction des versions du serveur et l’UI Skype paramètre. Le tableau ci-dessous montre l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Expérience du client**|
|:-----|:-----|:-----|
|Skype Entreprise Server |Par défaut  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server  |True  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server  |Faux  <br/> |Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)  <br/> |Par défaut  <br/> |Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)  <br/> |True  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)  <br/> |Faux  <br/> |Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Utilisateur invité à passer en mode Lync (l’utilisateur ne peut pas opter pour Skype pour les entreprises plus tard)  <br/> |
   
Le tableau suivant présente l’expérience du client lorsque l’administrateur modifie la valeur initiale de l’expérience Skype UI :
  

|**Version du serveur**|**Paramètre EnableSkypeUI**|**Interface utilisateur du client = Lync**|**UI client = Skype Entreprise**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Server |True  <br/> |Utilisateur invité à passer à Skype pour les entreprises  <br/> |Skype Entreprise  <br/> |
|Skype Entreprise Server |Faux  <br/> |Mode de Lync  <br/> |Utilisateur invité à passer en mode de Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)  <br/> |True  <br/> |Utilisateur invité à passer à Skype pour les entreprises  <br/> |Skype Entreprise  <br/> |
|Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)  <br/> |Faux  <br/> |Mode de Lync  <br/> |Utilisateur invité à passer en mode de Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sans correctifs)  <br/> |Par défaut  <br/> |Mode Lync (ne peuvent pas passer à Skype pour les entreprises)  <br/> |Mode Lync (ne peuvent pas passer à Skype pour les entreprises)  <br/> |
   
Les versions de correctif requises pour gérer la configuration de la Skype pour client d’entreprise sont les suivants :
  
- Lync Server 2010 - février 2015 mise à jour Cumulative (4.0.7577.710) pour Lync Server 2010. Pour plus d’informations, voir [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-2014 décembre mise à jour Cumulative (5.0.8308.857) pour Lync Server 2013. Pour plus d’informations, voir [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Création d'un objet de stratégie de groupe pour modifier le registre sur un ordinateur joint au domaine

La mise à jour dans le Registre pour afficher l’expérience du client Lync la première fois qu’un utilisateur lance le Skype pour Business 2015 client doit être effectuée qu’une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0. 
  
La procédure suivante décrit comment modifier le Registre afin que l’expérience du client Lync s’affiche la première fois qu’un utilisateur lance le Skype pour client Business 2015. Vous pouvez également utiliser cette procédure de mise à jour du registre pour désactiver le didacticiel de l’écran d’accueil comme décrit précédemment.
  
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
    
Ensuite, vous devez lier l'objet GPO créé au groupe d'utilisateurs auquel vous voulez affecter la stratégie, par exemple, une unité d'organisation.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Pour utiliser l'objet GPO pour affecter la stratégie

1. Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l'unité d'organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.
    
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
  

