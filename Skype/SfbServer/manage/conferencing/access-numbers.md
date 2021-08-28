---
title: 'Gérer les numéros d’accès aux conférences dans Skype Entreprise Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Résumé : Découvrez comment gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: fd1d32ff82fc7bd922acfaea567780b5683eb684
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621070"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gérer les numéros d’accès aux conférences dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server.
  
Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros apparaissent dans les invitations à une réunion et sur la page Web des paramètres de configuration des conférences rendez-vous. 
  
Cette rubrique décrit comment afficher, modifier ou supprimer des numéros d’accès aux conférences téléphoniques. Pour plus d’informations sur la création de numéros d’accès initiaux, voir [Configure dial-in conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Afficher les numéros d’accès aux conférences téléphoniques

Vous pouvez afficher les numéros d’accès aux conférences à l’aide Skype Entreprise Server panneau de Skype Entreprise Server Management Shell.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Afficher les numéros d’accès à l’aide Skype Entreprise Server panneau de bord

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**
    
4. Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.
    
5. Dans **Modifier,** cochez **la case Afficher les détails.**
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Afficher les numéros d’accès à l’aide Skype Entreprise Server Management Shell

Pour afficher des informations sur les numéros d’accès aux appels, utilisez l';cmdlet **Get-CsDialInConferencingAccessNumber.**
  
La commande suivante retourne une collection de tous les numéros d’accès aux conférences téléphoniques configurés pour être utilisés dans l’organisation : 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Voici un exemple du type d’informations renvoyé :
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Pour plus d’informations, [voir Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modifier les numéros d’accès aux conférences téléphoniques

Vous pouvez modifier les numéros d’accès à l’Skype Entreprise Server à l’aide du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modifier les numéros d’accès à l’aide du Skype Entreprise Server de contrôle d’accès

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**
    
4. Dans **la** page Numéro d’accès, cliquez sur l’un des numéros d’accès à la connexion dans la liste, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**
    
    > [!NOTE]
    > L’utilisation du champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès à la connexion risque de ne pas produire les résultats que vous attendez. Au lieu de cela, tiez la liste par colonne d’intérêt pour identifier le numéro d’accès à la connexion que vous souhaitez afficher ou modifier. 
  
5. Dans **le numéro d’affichage,** tapez le numéro de téléphone composé par les utilisateurs du réseau téléphonique commuté (PSTN) pour participer à une conférence. 
    
    Ce numéro s’affiche dans les invitations aux réunions et sur la page web Paramètres conférence rendez-vous.
    
6. Dans **nom d’affichage,** tapez une description pour le numéro d’accès à la connexion. Il s’agit du nom associé au numéro d’accès à la connexion dans les Skype Entreprise de recherche.
    
    Ce nom s’affiche dans le client lorsqu’un utilisateur appelle le numéro d’accès. 
    
7. Dans **l’URI** de ligne, tapez le numéro E.164 du numéro d’accès à la numérotation au format URI TEL, en incluant le symbole + avant le numéro et en excluant les espaces. Par exemple, tel:+14255550200.
    
    > [!NOTE]
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès aux conférences téléphoniques. 
  
8. Dans **l’URI SIP,** faites les choses suivantes :
    
   Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès de conférence. Cet URI SIP s’affiche à différents emplacements, y compris, mais sans s’y limiter, les messages de notification d’appel et les versions précédentes des clients Lync.
    
    > [!NOTE]
    > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès de conférence. L’URI SIP ne peut pas être modifié après la création du numéro d’accès. La seule façon de modifier l’URI SIP consiste à supprimer et à recréer le numéro d’accès. 
  
   Dans la zone de liste liste, cliquez sur le domaine du application Assistant de conférence qui prend en charge ce numéro d’accès à la connexion.
    
9. Dans **pool,** cliquez sur le pool qui exécute l’instance de Assistant de conférence qui prend en charge ce numéro d’accès à la connexion.
    
    > [!NOTE]
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’cmdlet **Move-CsApplicationEndpoint** ou supprimer et recréer le numéro d’accès.
  
10. Dans **la langue principale,** cliquez sur la langue dans laquelle les invites sont lées pour ce numéro d’accès à la connexion. 
    
    La langue principale est la langue que le Assistant de conférence utilise pour répondre à l’appel. Les langues prise en charge sont affichées avec chaque numéro de téléphone d’accès sur la page web conférence Paramètres conférences.
    
11. (Facultatif) Dans **les langues** secondaires (maximum de quatre) , cliquez sur Ajouter, sélectionnez une ou plusieurs langues supplémentaires que vous souhaitez prendre en charge pour les appelants à ce numéro d’accès, puis cliquez sur  **OK.** 
    
    Vous pouvez choisir jusqu’à quatre langues secondaires pour chaque numéro d’accès à la connexion. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de conférence lorsqu’ils participent à une conférence.
    
12. Pour ajouter une région pour le numéro d’accès à la connexion, sous Régions associées, cliquez sur **Ajouter,** cliquez sur une ou plusieurs régions associées aux plans de numérotation pour ce numéro d’accès, puis cliquez sur **OK.**
    
13. Pour supprimer une région du numéro d’accès à la connexion, sous Régions **associées,** cliquez sur la région à supprimer, puis cliquez sur **Supprimer.**
    
14. Cliquez sur **Valider**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modifier les numéros d’accès à l’aide Skype Entreprise Server Management Shell

Pour modifier les numéros d’accès aux appels, utilisez l’cmdlet **Set-CsDialInConferencingAccessNumber.**
  
La commande suivante modifie la propriété DisplayName du numéro d’accès à la conférence téléphonique dont l’identité est sip:RedmondDialIn@litwareinc.com. Dans cet exemple, le nom complet est « Redmond Dial-In Access Number » :
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Dans l’exemple suivant, le numéro d’accès aux conférences téléphoniques avec l’identité sip:RedmondDialIn@litwareinc.com est modifié pour inclure deux régions : Redmond et Seattle. Pour cela, le paramètre Region est appelé, suivi des deux régions (deux valeurs de chaînes séparées par une virgule). Notez que cette commande échouera si les deux régions, Redmond et Seattle, ne sont pas déjà définies dans des plans de numérotation.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Pour plus d’informations, [voir Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Supprimer un numéro d’accès aux conférences téléphoniques

Vous pouvez supprimer un numéro d’accès aux conférences téléphoniques à l’aide du Panneau de Skype Entreprise Server ou de l’Skype Entreprise Server Management Shell.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Supprimer un numéro d’accès aux conférences conférences à l’aide Skype Entreprise Server panneau de bord

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**
    
4. Dans la page, cliquez sur le numéro de connexion à supprimer dans la liste, cliquez sur **Modifier,** puis cliquez sur **Supprimer.**
    
5. Cliquez sur **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Supprimer un numéro d’accès aux conférences à l’aide de Skype Entreprise Server Management Shell

Pour supprimer un numéro d’accès aux conférences téléphoniques, utilisez **Remove-CsDialInConferencingAccessNumber**.
  
La commande suivante supprime le numéro d’accès aux conférences téléphoniques avec l’identité sip:RedmondDialInAccess@litwareinc.com :
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

La commande suivante supprime tous les numéros d’accès aux conférences téléphoniques associés à la région Northwest :
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

La commande suivante supprime tous les numéros d’accès aux conférences téléphoniques dont l’italien est la langue principale :
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Pour plus d’informations, [voir Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
