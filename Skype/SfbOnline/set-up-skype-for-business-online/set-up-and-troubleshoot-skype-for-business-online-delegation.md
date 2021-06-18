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
description: Cet article explique comment configurer et dépanner la délégation Skype Entreprise Online. Cet article fournit des conseils sur la configuration, les recommandations et les étapes de dépannage.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010797"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online

Cet article explique comment configurer et dépanner la délégation Skype Entreprise Online. Cet article fournit des conseils sur la configuration, les recommandations et les étapes de dépannage.
  
## <a name="guidelines-and-requirements"></a>Instructions et exigences

### <a name="guidelines-for-delegation"></a>Instructions relatives à la délégation

La configuration et la configuration de la délégation pour qu’elle fonctionne correctement dépendent de vos recommandations :
  
- Vous devez utiliser le client complet Skype Entreprise 2015 avec les dernières mises à jour ou le client Skype Entreprise 2016 complet.
    
- Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.
    
- Assurez-vous que le délégant et les ordinateurs délégués ont un profil de courrier Outlook principal ou le profil par défaut. Ce profil de messagerie ne doit contenir qu’un seul compte.
    
- Skype Entreprise pour le délégant et le délégué doivent être des utilisateurs en ligne. En outre, les Exchange Server de messagerie pour chaque compte doivent être soit en ligne, soit sur site.
    
- Le délégant et le délégué doivent utiliser la même version principale d’Outlook.
    
- La **valeur de l’attribut EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie client. Vous pouvez vérifier ce paramètre en exécutant l’cmdlet **Get-CSClientPolicy** dans le module PowerShell de Skype Entreprise Online.
    
- Le délégant et le délégué doivent être inscrits à Skype Entreprise et à Outlook en même temps sur différentes stations de travail.
    
- Les boîtes aux lettres partagées ne sont pas prise en charge pour la délégation Skype Entreprise Online. Cela est dû au fait que la boîte aux lettres partagée ne comprend pas de liste de contrôle d’accès (ACL) **de** la part de l’expéditeur.
    
### <a name="skype-for-business-client-version-support"></a>Prise en charge de la version du client Skype Entreprise

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Client Lync/Skype Entreprise Basic**| Non pris en charge |Non pris en charge
|**Skype Entreprise 2015**|Pris en charge | Pris en charge|
|**Skype Entreprise 2016**|Pris en charge | Pris en charge|

   
### <a name="licensing-requirements"></a>Conditions de licence requises

**Scénario de licence Entreprise E3**

|**Licence**|**Clients**|**Notes**|
|:-----|:-----|:-----|
|Entreprise E3  <br/> |Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Le client Skype Entreprise Basic ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
|Entreprise E3 avec Office 365 Phone System + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Le client Skype Entreprise Basic ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
   
**Scénario de licence Entreprise E5**

|**Licence**|**Clients**|**Notes**|
|:-----|:-----|:-----|
|Entreprise E5  <br/> |Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016.  <br/> Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Le client Skype Entreprise Basic ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
|Entreprise E5 + Plan d’appel Office 365  <br/> |Skype Entreprise pour Mac 2016  <br/> Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Le client Skype Entreprise Basic ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurer et vérifier la délégation

Pour configurer la délégation Skype Entreprise Online, suivez ces étapes :
  
### <a name="for-windows-clients"></a>Pour les clients Windows

 **Onglet De forwarding d’appel**
  
1. Sélectionnez **Options**  >    >  **Outils Paramètres de forwardage d’appel.**
    
2. Sélectionnez **Modifier mes membres délégués.**
    
3. **Sélectionnez** Ajouter, sélectionnez le délégué que vous voulez ajouter, puis **OK.**
    
 **Aucun onglet De forwarding d’appel**
  
1. Dans Outlook, sélectionnez  >  **Paramètres du compte de fichier**- Ajouter un  >  **accès**  >  **délégué.**
    
2. Localisez et ajoutez le nom de la personne qui sera déléguée.
    
3. Sélectionnez **le** menu Calendrier, puis Sélectionnez **Éditeur (peut lire, créer et modifier des éléments).**
    
### <a name="for-mac-clients---lync"></a>Pour les clients Mac - Lync

 **Onglet De forwarding d’appel**
  
- Si le client ne  dispose pas d’un  onglet Dedélément d’appel avec le lien Modifier mes membres délégués et que le délégant se trouve sur un ordinateur Mac, le délégant doit se connecter à un ordinateur Windows pour configurer la délégation. En effet, les clients Mac ne peuvent pas établir de connexions MAPI, et il s’agit d’une obligation d’établir la délégation Skype Entreprise à partir d’Outlook.
    
### <a name="verify-success"></a>Vérifier la réussite

Si la configuration réussit, le délégué doit voir que vous avez été ajouté en tant que délégué du message **< Name>** et que le groupe Personnes **que** je gère les appels est créé. Le délégant doit voir que le groupe **Délégués** est créé.
  
> [!NOTE]
> Les autorisations de délégation apparaissent généralement dans les 30 minutes après le processus de configuration. Toutefois, cette procédure peut prendre jusqu’à 24 heures. 
  
## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="common-issues"></a>Problèmes courants

- > **Problème 1** L’entrée de délégué continue d’apparaître dans le groupe Personnes **je** gère les appels pour une fois que le délégant a supprimé le délégué du client Outlook.
    
  - > **Résolution 1** Dans le client Skype Entreprise, cliquez avec le bouton droit sur le délégué dans le groupe **Délégués,** puis sélectionnez Supprimer **du groupe.**
    
- > **Problème 2** Une fois l’accès délégué accordé par le biais du client Outlook, ni le message de confirmation ni le message « Personnes **que** je gère les appels pour le groupe » n’apparaissent pour le délégué.
    
  - > **Résolution 2** Supprimez la délégation du client Outlook, attendez environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.
    
### <a name="other-common-issues"></a>Autres problèmes courants

- La délégation ne fonctionne pas si le seuil de 25 délégations et 25 délégués est dépassé.
    
- Le client Skype Entreprise Basic n’est pas pris en charge.
    
    > [!NOTE]
    > Si vous installez le client Skype Entreprise Basic, la délégation est supprimée. 
  
- Si la **valeur État MAPI** n’est pas **CORRECTE,** assurez-vous que les valeurs **SIP** et **SMTP** correspondent.
    
    > [!NOTE]
    > Après le premier démarrage de Skype Entreprise  et Outlook, l’affichage du statut MAPI peut prendre plusieurs minutes.
  
- La création d’un groupe de sécurité et l’ajout d’autorisations de délégation à ce groupe de sécurité ne sont pas pris en charge.
    
- MAPI n’est pas disponible. Consultez [l’erreur « MAPI non disponible » dans le client Skype Entreprise 2016.](https://support.microsoft.com/help/3147130)
    
- La boîte aux lettres Exchange Online n’est pas accessible via le client Skype Entreprise. Si c’est le cas, exécutez le [test de connectivité d’Outlook](https://testconnectivity.microsoft.com/) pour vous assurer qu’il est exécuté.
    
## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
