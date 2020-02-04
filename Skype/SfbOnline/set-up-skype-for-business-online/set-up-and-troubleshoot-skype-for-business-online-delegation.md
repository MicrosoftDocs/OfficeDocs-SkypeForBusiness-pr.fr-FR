---
title: Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Cet article explique comment configurer et résoudre les problèmes de délégation Skype entreprise online. Cet article fournit des conseils pour la configuration des recommandations, meilleures pratiques et étapes de résolution des problèmes.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706479"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online

Cet article explique comment configurer et résoudre les problèmes de délégation Skype entreprise online. Cet article fournit des conseils pour la configuration des recommandations, meilleures pratiques et étapes de résolution des problèmes.
  
## <a name="guidelines-and-requirements"></a>Recommandations et configuration requise

### <a name="guidelines-for-delegation"></a>Recommandations en matière de délégation

La configuration et l’activation de la délégation fonctionneront correctement en fonction des recommandations suivantes :
  
- Vous devez utiliser le client complet Skype entreprise 2015 avec les mises à jour les plus récentes ou le client complet Skype entreprise 2016.
    
- Vous devez utiliser le client Outlook 2013 avec les mises à jour les plus récentes ou le client 2016 Outlook.
    
- Assurez-vous que la personne qui est déléguée et déléguée ont un profil de courrier Outlook principal ou le profil par défaut. Ce profil de messagerie ne doit contenir qu’un seul compte.
    
- Skype entreprise pour le déléguer et le délégué doivent être des utilisateurs en ligne. Par ailleurs, les boîtes aux lettres Exchange Server pour chaque compte doivent être soit en ligne soit en local.
    
- Le délégué et le délégué doivent utiliser la même version majeure d’Outlook.
    
- La valeur de l’attribut **EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie client. Vous pouvez vérifier ce paramètre en exécutant l’applet de contrôle **Get-CSClientPolicy** dans le module PowerShell de Skype entreprise online.
    
- Le délégué et le délégué doivent être connectés à Skype entreprise et à Outlook en même temps sur différentes stations de travail.
    
- Les boîtes aux lettres partagées ne sont pas prises en charge pour la délégation Skype entreprise online. En effet, la boîte aux lettres partagée ne dispose pas de la liste de contrôle d’accès **SendOnBehalf** (ACL).
    
### <a name="skype-for-business-client-version-support"></a>Prise en charge du client Skype entreprise

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Client de base Lync/Skype entreprise**| Non pris en charge |Non pris en charge
|**Skype Entreprise 2015**|Pris en charge | Pris en charge|
|**Skype entreprise 2016**|Pris en charge | Pris en charge|

   
### <a name="licensing-requirements"></a>Conditions de licence

**Scénario de gestion des licences entreprise E3**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|Entreprise E3  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Le client Skype entreprise basique ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
|Entreprise E3 avec le système téléphonique d’Office 365 + plan Office 365 xCalling  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Le client Skype entreprise basique ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
   
**Scénario de gestion des licences entreprise E5**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|Entreprise E5  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016.  <br/> Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Le client Skype entreprise basique ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
|Plan d’appel d’entreprise E5 et Office 365  <br/> |Skype entreprise pour Mac 2016  <br/> Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Le client Skype entreprise basique ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurer et vérifier la délégation

Pour configurer la délégation de Skype entreprise Online, procédez comme suit :
  
### <a name="for-windows-clients"></a>Pour les clients Windows

 **Onglet renvoi d’appel**
  
1. Sélectionnez **Outils** > **options** > **paramètres de transfert d’appel**.
    
2. Cliquez sur **Modifier mes membres délégués**.
    
3. Cliquez sur **Ajouter**, sélectionnez le délégué que vous voulez ajouter, puis sélectionnez **OK**.
    
 **Aucun onglet renvoi d’appel**
  
1. Dans Outlook, sélectionnez **** > **paramètres** > du compte de fichier > **Ajouter****l’accès délégué**.
    
2. Recherchez et ajoutez le nom de la personne qui va agir en tant que délégué.
    
3. Sélectionnez le menu **calendrier** , puis **éditeur (peut lire, créer et modifier des éléments)**.
    
### <a name="for-mac-clients---lync"></a>Pour les clients Mac-Lync

 **Onglet renvoi d’appel**
  
- Si le client ne possède pas d’onglet **renvoi d’appel** avec le lien **Modifier mes membres délégués** et si la personne disposant se trouve sur un ordinateur Mac, la personne disposant doit se connecter à un ordinateur exécutant Windows pour configurer la délégation. En effet, les clients Mac ne peuvent pas créer de connexions MAPI et c’est une condition requise pour établir une délégation Skype entreprise à partir d’Outlook.
    
### <a name="verify-success"></a>Vérifier le succès

Si la configuration est réussie, le délégué doit voir le message **vous avez été ajouté en tant que délégué pour < nom>** message et les **personnes avec lesquelles je gère les appels pour** le groupe sont créées. La personne disposant doit voir que le groupe **délégués** est créé.
  
> [!NOTE]
> Les autorisations de délégation apparaissent généralement dans les 30 minutes du processus d’installation. Toutefois, ce processus peut prendre jusqu’à 24 heures. 
  
## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="common-issues"></a>Problèmes courants

- > **Problème 1** L’entrée de délégué continue à apparaître dans le groupe **personnes que je gère** , une fois que le délégué a supprimé le délégué du client Outlook.
    
  - > **Résolution 1** Sur le client Skype entreprise, cliquez avec le bouton droit sur le délégué dans le groupe **délégués** , puis sélectionnez **supprimer du groupe**.
    
- > **Problème 2** Lorsque l’accès délégué est accordé par le biais du client Outlook, ni le message de confirmation, ni le message **je gère les appels pour** le délégué apparaissent.
    
  - > **Résolution 2** Supprimez la délégation du client Outlook, attendez environ 15 minutes pour la réplication, puis rajoutez le délégué.
    
### <a name="other-common-issues"></a>Autres problèmes courants

- La délégation ne fonctionne pas si le seuil de 25 délégations et 25 délégués est dépassé.
    
- Le client Skype entreprise basique n’est pas pris en charge.
    
    > [!NOTE]
    > Si vous installez le client Skype entreprise Basic, il est supprimé et interrompu la délégation. 
  
- Si la valeur de **statut MAPI** n’est pas **OK**, assurez-vous que les valeurs **SIP** et **SMTP** correspondent.
    
    > [!NOTE]
    > Quelques minutes peuvent s’écouler avant que l’État MAPI affiche le message **OK** une fois que vous avez démarré Skype entreprise et Outlook.
  
- La création d’un groupe de sécurité et l’ajout d’autorisations de délégation pour ce groupe de sécurité ne sont pas prises en charge.
    
- MAPI n’est pas disponible. Voir [erreur « MAPI non disponible » dans le client Skype entreprise 2016](https://support.microsoft.com/en-us/help/3147130).
    
- La boîte aux lettres Exchange Online n’est pas accessible via le client Skype entreprise. Le cas échéant, exécutez le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) pour vérifier qu’il est transmis.
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
