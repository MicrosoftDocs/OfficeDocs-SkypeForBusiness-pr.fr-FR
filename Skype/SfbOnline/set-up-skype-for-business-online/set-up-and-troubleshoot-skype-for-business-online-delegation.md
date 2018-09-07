---
title: Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Cet article explique comment configurer et dépanner Skype pour la délégation d’entreprise en ligne. Cet article vous donne des conseils pour les étapes de dépannage, meilleures pratiques et recommandations pour le programme d’installation.
ms.openlocfilehash: bb1f8639d045d156d5095e33a4a012987604c6e1
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856488"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online

Cet article explique comment configurer et dépanner Skype pour la délégation d’entreprise en ligne. Cet article vous donne des conseils pour les étapes de dépannage, meilleures pratiques et recommandations pour le programme d’installation.
  
## <a name="guidelines-and-requirements"></a>Instructions et conditions requises

### <a name="guidelines-for-delegation"></a>Instructions pour la délégation

Configuration et l’obtention de la délégation fonctionne correctement dépendent de vous les recommandations suivantes :
  
- Vous devez utiliser le Skype pour client complète 2015 métier avec les dernières mises à jour ou le Skype pour client complète 2016 Business.
    
- Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.
    
- Assurez-vous que la personne et des ordinateurs délégués ont un profil de messagerie Outlook est le principal ou le profil par défaut. Ce profil de messagerie doit contenir qu’un seul compte.
    
- Skype pour les entreprises pour la personne qui a délégué et le délégué doit être des utilisateurs en ligne. En outre, les boîtes aux lettres Exchange Server pour chaque compte doit soit les deux être en ligne ou locale.
    
- La personne qui a délégué et le délégué doivent être à l’aide de la même version principale de Microsoft Outlook.
    
- La valeur d’attribut **EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie du client. Vous pouvez vérifier ce paramètre en exécutant l’applet de commande **Get-CSClientPolicy** dans la Skype pour le module Business Online PowerShell.
    
- La personne qui a délégué et le délégué doivent être connectés à Skype pour les entreprises et Outlook en même temps sur des stations de travail.
    
- Boîtes aux lettres partagées ne sont pas pris en charge pour Skype pour la délégation d’entreprise en ligne. Il s’agit, car la liste de contrôle d’accès (ACL) **sendonbehalf** ne possède pas de la boîte aux lettres partagée.
    
### <a name="skype-for-business-client-version-support"></a>Skype pour la prise en charge de la version entreprise client

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype pour le Client de base Business**| Non pris en charge |Non pris en charge
|**Skype Entreprise 2015**|Pris en charge| Pris en charge|
|**Skype pour Business 2016**|Pris en charge| Pris en charge|

   
### <a name="licensing-requirements"></a>Conditions de licence

**Scénario de licence entreprise E3**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|Entreprise E3  <br/> |Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016  <br/> |Skype pour le client Business base ne gère pas la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.  <br/> |
|Entreprise E3 avec Office 365 Phone System + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype pour le client Business base ne gère pas la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.  <br/> |
   
**Scénario de licence entreprise E5**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|E5 d’entreprise  <br/> |Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou 2016 Outlook.  <br/> Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016  <br/> |Skype pour le client Business base ne gère pas la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.  <br/> |
|E5 Enterprise plus Plan d’appel Office 365  <br/> |Skype pour les entreprises pour Mac 2016  <br/> Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype pour le client Business base ne gère pas la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurer et vérifier la délégation

Pour configurer Skype pour la délégation d’entreprise en ligne, procédez comme suit :
  
### <a name="for-windows-clients"></a>Pour les clients Windows

 **Onglet de transfert d’appel**
  
1. Sélectionnez **Outils** > **Options** > **paramètres de transfert d’appel**.
    
2. Sélectionnez **Modifier mes membres délégués**.
    
3. Sélectionnez **Ajouter**, sélectionnez le délégué que vous souhaitez ajouter, puis sélectionnez **OK**.
    
 **Aucun onglet transfert d’appel**
  
1. Dans Outlook, sélectionnez le **fichier** > **Paramètres du compte** > **Accès délégué** > **Ajouter**.
    
2. Recherchez, puis ajoutez le nom de la personne qui doit être le délégué.
    
3. Sélectionnez le menu **calendrier** , puis sélectionnez **éditeur (peut lire, créer et modifier des éléments)**.
    
### <a name="for-mac-clients---lync"></a>Pour les clients Mac - Lync

 **Onglet de transfert d’appel**
  
- Si le client ne possède pas un onglet **Transfert d’appel** qui contient le lien **Modifier mes membres délégués** , et la personne qui se trouve sur un ordinateur Mac, la personne doit se connecter à un ordinateur fonctionnant sous Windows afin de configurer la délégation. Il s’agit, car les clients Mac ne peut pas établir des connexions de MAPI, et il s’agit d’une condition requise pour établir une relation Skype pour la délégation d’entreprise à partir d’Outlook.
    
### <a name="verify-success"></a>Vérifier la réussite

Si le programme d’installation se déroule correctement, le délégué doit voir **que vous avez été ajouté en tant que délégué pour < nom >** message et que le groupe de **personnes dont je gérer les appels pour** est créé. La personne qui a délégué doit voir que le groupe de **délégués** est créé.
  
> [!NOTE]
> Autorisations de délégation apparaissent généralement dans les 30 minutes au processus d’installation. Toutefois, ce processus peut prendre jusqu'à 24 heures. 
  
## <a name="troubleshooting"></a>Identification et résolution des problèmes

### <a name="common-issues"></a>Problèmes courants

- > **Problème 1** L’entrée de délégué continue d’apparaître dans le groupe de **personnes dont je gérer les appels pour** une fois que la personne a supprimé le délégué à partir du client Outlook.
    
  - > **Résolution 1** Sur Skype pour client d’entreprise, le délégué dans le groupe **délégués** d’avec le bouton droit et sélectionnez **Supprimer du groupe**.
    
- > **Problème 2** Une fois que l’accès délégué est accordé via le client Outlook, le message de confirmation, ni le groupe de **personnes dont je gérer les appels pour** s’affichent pour le délégué.
    
  - > **Résolution 2** Supprimer la délégation à partir du client Outlook, attendez environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.
    
### <a name="other-common-issues"></a>Autres problèmes courants

- Délégation ne fonctionne pas si le seuil de 25 délégués et les personnes qui 25 délèguent est dépassé.
    
- Le Skype pour le client Business base n’est pas pris en charge.
    
    > [!NOTE]
    > Si vous installez le Skype pour le client Business base, supprime et rompre la délégation. 
  
- Si la valeur **d’État MAPI** n’est pas **OK**, assurez-vous que les valeurs **SIP** et **SMTP** correspondent.
    
    > [!NOTE]
    > Il peut prendre quelques minutes pour que le statut MAPI à afficher en tant que **OK** une fois que vous commencez Skype pour les entreprises et Outlook.
  
- Création d’un groupe de sécurité et ajout d’autorisations de délégation pour ce groupe de sécurité n’est pas pris en charge.
    
- MAPI n’est pas disponible. Voir [l’Erreur « MAPI non disponible » dans Skype pour 2016 Business client](https://support.microsoft.com/en-us/help/3147130).
    
- La boîte aux lettres Exchange Online n’est pas accessible via le Skype pour client d’entreprise. Si cela se produit, exécutez le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) pour vous assurer qu’il passe.
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 