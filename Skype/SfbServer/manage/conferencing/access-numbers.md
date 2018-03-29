---
title: Gestion des numéros d’accès aux conférences rendez-vous dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Résumé : Apprenez à gérer les numéros d’accès à distance de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: ebe3388578b74041802afc12f47e0b484cb88bd7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server-2015"></a>Gestion des numéros d’accès aux conférences rendez-vous dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer les numéros d’accès à distance de conférence dans Skype pour Business Server 2015.
  
Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous. 
  
Cette rubrique décrit comment afficher, modifier ou supprimer des numéros d’accès à des conférences rendez-vous. Pour plus d’informations sur la façon de créer des numéros d’accès à distance initiale, reportez-vous à [configurer à distance conférence dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Affichage des numéros d’accès aux conférences rendez-vous

Vous pouvez afficher les numéros d’accès à distance dans la conférence à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Afficher les numéros d’accès à distance à l’aide de Skype pour le panneau de configuration de Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.
    
4. Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.
    
5. Dans **Modifier**, activez la case à cocher **Afficher les détails**.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Afficher les numéros d’accès à distance à l’aide de Skype pour Business Server Management Shell

Pour afficher des informations sur des numéros d’accès à des conférences rendez-vous, utilisez l’applet de commande **Get-Cs DialInConferencingAccessNumber**.
  
La commande suivante retourne une collection de tous les numéros d’accès conférence à distance configurés pour être utilisés dans l’organisation : 
  
```
Get-CsDialInConferencingAccessNumber

```

Voici un exemple du type d’informations renvoyées :
  
```
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

```

Pour plus d’informations, consultez [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modification des numéros d’accès à des conférences rendez-vous

Vous pouvez modifier les numéros d’accès à distance à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modifier les numéros d’accès à distance à l’aide de Skype pour le panneau de configuration de Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.
    
4. Dans la page **Numéro d’accès entrant**, cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
    > [!NOTE]
    > Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier. 
  
5. Dans **Numéro affiché**, tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence. 
    
    Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.
    
6. In **Nom d’affichage**, tapez la description du numéro d’accès entrant. Il s’agit de celui qui est associé au numéro d’accès à distance dans Skype pour les résultats de la recherche.
    
    Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès. 
    
7. Dans **URI de ligne**, tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.
    
    > [!NOTE]
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. 
  
8. Dans **URI SIP**, procédez comme suit :
    
   Dans la zone de texte, tapez un URI SIP (Session Initiation Protocol) unique pour ce numéro d’accès à une conférence rendez-vous. Cet URI SIP est affiché dans divers emplacements, y compris, mais non limité, pour appeler des messages de notification et les versions antérieures de clients Lync.
    
    > [!NOTE]
    > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès. 
  
   Dans la zone de liste déroulante, cliquez sur le domaine de l’application de la surveillance du conférence qui prend en charge ce nombre d’accès à distance.
    
9. Dans **Pool**, cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.
    
    > [!NOTE]
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande **Move-CsApplicationEndpoint** ou supprimer et recréer le numéro d’accès.
  
10. Dans **Langue principale**, cliquez sur la langue des invites pour ce numéro d’accès entrant. 
    
    La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.
    
11. (Facultatif) Dans **Langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK**. 
    
    Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.
    
12. Pour ajouter une région pour le numéro d’accès à distance, dans **les régions associés**, cliquez sur ** Ajouter **, cliquez sur une ou plusieurs zones qui sont associés à des plans de numérotation de ce numéro d’accès à distance, puis cliquez sur **OK**.
    
13. Pour supprimer une région du numéro d’accès entrant, sous **Régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
    
14. Cliquez sur **Valider**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modifier les numéros d’accès à distance à l’aide de Skype pour Business Server Management Shell

Pour modifier des numéros d’accès aux conférences rendez-vous, utilisez l’applet de commande **Set-Cs DialInConferencingAccessNumber**.
  
La commande ci-dessous modifie la propriété DisplayName pour le numéro d’accès de conférence rendez-vous avec la propriété Identity sip:RedmondDialIn@litwareinc.com. Dans cet exemple, le nom complet est défini sur « Redmond Dial-In Access Number » :
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"

```

Dans l’exemple ci-dessous, le numéro d’accès de conférence rendez-vous avec la propriété Identity sip:RedmondDialIn@litwareinc.com est modifié pour inclure deux régions : Redmond et Seattle. Pour cela, le paramètre Region est appelé, suivi des deux régions (deux valeurs de chaînes séparées par une virgule). Notez que cette commande échouera si les deux régions, Redmond et Seattle, ne sont pas déjà définies dans des plans de numérotation.
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"

```

Pour plus d’informations, voir [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Suppression d’un numéro d’accès de conférence rendez-vous

Vous pouvez supprimer un numéro d’accès à distance dans la conférence à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Supprimer un numéro d’accès à distance de conférence pour le panneau de configuration de Business Server à l’aide de Skype

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.
    
4. Dans la page, cliquez sur le numéro d’accès que vous souhaitez supprimer dans la liste, cliquez sur **Modifier**, puis sur **Supprimer**.
    
5. Cliquez sur **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Supprimer un numéro d’accès à distance dans la conférence à l’aide de Skype pour Business Server Management Shell

Pour supprimer un numéro d’accès de conférence rendez-vous, utilisez l’applet de commande **Remove-CsDialInConferencingAccessNumber**.
  
La commande ci-dessous permet de supprimer le numéro d’accès de conférence rendez-vous doté de l’ID sip:RedmondDialInAccess@litwareinc.com :
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

La commande ci-dessous permet de supprimer tous les numéros d’accès de conférence rendez-vous associés à la région Northwest :
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

La commande ci-dessous permet de supprimer tous les numéros d’accès de conférence rendez-vous où l’italien est la langue principale :
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Pour plus d’informations, consultez [Supprimer-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

