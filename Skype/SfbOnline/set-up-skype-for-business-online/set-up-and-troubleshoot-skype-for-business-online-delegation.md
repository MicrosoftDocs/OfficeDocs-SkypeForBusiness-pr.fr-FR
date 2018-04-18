---
title: Configurer et dépanner Skype pour la délégation d’entreprise en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Cet article explique comment configurer et dépanner Skype pour la délégation d’activité en ligne. Cet article vous donne des conseils pour des recommandations sur le paramétrage, les meilleures pratiques et les étapes de dépannage.
ms.openlocfilehash: 13df45590905bd6bbf7498ec6d2ab912cf976228
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurer et dépanner Skype pour la délégation d’entreprise en ligne

Cet article explique comment configurer et dépanner Skype pour la délégation d’activité en ligne. Cet article vous donne des conseils pour des recommandations sur le paramétrage, les meilleures pratiques et les étapes de dépannage.
  
## <a name="guidelines-and-requirements"></a>Instructions et conditions

### <a name="guidelines-for-delegation"></a>Instructions pour la délégation

Paramétrage et mise en route de la délégation fonctionne correctement dépendant de vous les recommandations suivantes :
  
- Vous devez utiliser le Skype pour client complet d’entreprise 2015 avec les dernières mises à jour ou le Skype pour le client complet de 2016 de l’entreprise.
    
- Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.
    
- Assurez-vous que la personne qui a délégué et délégué ordinateurs ont un profil de messagerie Outlook est le principal ou le profil par défaut. Ce profil de messagerie doit contenir qu’un seul compte.
    
- Skype pour les entreprises de la personne qui a délégué et du délégué doit être des utilisateurs en ligne. En outre, les boîtes aux lettres Exchange Server pour chaque compte doit soit tous les deux être en ligne ou sur site.
    
- La personne qui a délégué et le délégué doivent utiliser la même version principale de Microsoft Outlook.
    
- La valeur de l’attribut **EnableExchangeDelegateSync** doit être définie à **true** dans la stratégie du client. Vous pouvez vérifier ce paramètre en exécutant l’applet de commande **Get-CSClientPolicy** dans le Skype pour module de Business Online PowerShell.
    
- La personne qui a délégué et le délégué doivent être connectés à Skype pour les entreprises et Outlook en même temps sur les stations de travail différentes.
    
- Boîtes aux lettres partagées ne sont pas pris en charge pour Skype pour la délégation d’activité en ligne. C’est parce que la boîte aux lettres partagée n’a pas la liste de contrôle d’accès (ACL) **sendonbehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Skype pour la prise en charge de la version Business client

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype pour Client de base d’entreprise**| Non pris en charge |Non pris en charge
|**Skype pour entreprise 2015**|Pris en charge| Pris en charge|
|**Skype pour entreprise 2016**|Pris en charge| Pris en charge|

   
### <a name="licensing-requirements"></a>Conditions de licence

**Scénario de licence entreprise E3**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|Entreprise E3  <br/> |Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Skype pour client de base d’entreprise ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.  <br/> |
|E3 Enterprise avec Office 365 téléphone système + d’Office 365, xCalling Plan  <br/> |Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype pour client de base d’entreprise ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.  <br/> |
   
**Scénario de licence entreprise E5**

|**Licence**|**Clients**|**Remarques**|
|:-----|:-----|:-----|
|E5 de l’entreprise  <br/> |Lync 2013 (Skype pour entreprise 2015) utilisé avec 2016 d’Outlook ou d’Outlook 2013.  <br/> Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016  <br/> |Skype pour client de base d’entreprise ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.  <br/> |
|E5 de l’entreprise plus de Plan d’appel de Office 365  <br/> |Skype pour entreprise pour Mac 2016  <br/> Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype pour client de base d’entreprise ne prend pas en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Permet de paramétrer et de vérifier la délégation

Pour paramétrer Skype pour la délégation d’entreprise en ligne, procédez comme suit :
  
### <a name="for-windows-clients"></a>Pour les clients Windows

 **Onglet de transfert d’appel**
  
1. Sélectionnez **Outils** > **Options** > **appeler le transfert des paramètres**.
    
2. Sélectionnez **Modifier les membres de mon délégué**.
    
3. Sélectionnez **Ajouter**et sélectionnez le délégué que vous souhaitez ajouter puis sélectionnez **OK**.
    
 **Aucun onglet transfert d’appel**
  
1. Dans Outlook, sélectionnez le **fichier** > **Les paramètres du compte** > **Accès délégué** > **Ajouter**.
    
2. Recherchez, puis ajoutez le nom de la personne qui va être le délégué.
    
3. Sélectionnez le menu **calendrier** , puis sélectionnez **éditeur (peut lire, créer et modifier des éléments)**.
    
### <a name="for-mac-clients---lync"></a>Pour les clients Mac - Lync

 **Onglet de transfert d’appel**
  
- Si le client n’a pas un onglet **Transfert d’appel** qui a le lien **Modifier les membres de mon délégué** et que la personne se trouve sur un ordinateur Mac, la personne doit vous connecter à un ordinateur fonctionnant sous Windows pour configurer la délégation. C’est parce que les clients Mac ne peut pas effectuer de connexions MAPI, et il s’agit d’une exigence pour établir Skype pour la délégation d’entreprise à partir d’Outlook.
    
### <a name="verify-success"></a>Vérifiez le succès

Si l’installation est réussie, le délégué doit s’afficher **que vous avez été ajouté en tant que délégué pour < nom >** message et que le groupe de **personnes je gérer les appels pour** est créé. La personne qui a délégué doit voir que le groupe de **délégués** est créé.
  
> [!NOTE]
> Autorisations de délégation apparaissent généralement dans les 30 minutes au processus d’installation. Toutefois, ce processus peut prendre jusqu'à 24 heures. 
  
## <a name="troubleshooting"></a>Identification et résolution des problèmes

### <a name="common-issues"></a>Problèmes courants

- > **Problème 1** L’entrée de délégué continue d’apparaître dans le groupe **I gérer les appels pour les personnes** après que la personne a retiré le délégué du client Outlook.
    
  - > **Résolution 1** Sur le Skype pour client d’entreprise, droit le délégué dans le groupe de **délégués** et sélectionnez **Supprimer du groupe**.
    
- > **Problème 2** Une fois l’accès délégué est accordé via le client Outlook, le message de confirmation, ni le groupe **I gérer les appels pour les personnes** s’affichent pour le délégué.
    
  - > **Résolution 2** Supprimer la délégation à partir du client Outlook, et attendre environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.
    
### <a name="other-common-issues"></a>Autres problèmes courants

- Délégation ne fonctionne pas si le seuil de personnes qui 25 délèguent et 25 délégués est dépassé.
    
- Le Skype pour client de base d’entreprise n’est pas pris en charge.
    
    > [!NOTE]
    > Si vous installez le Skype pour client de base d’entreprise, il supprime et rompre la délégation. 
  
- Si la valeur **d’État de MAPI** n’est pas **OK**, assurez-vous que les valeurs de **SIP** et **SMTP** correspondent.
    
    > [!NOTE]
    > Elle peut prendre plusieurs minutes pour que le statut MAPI à afficher comme **OK** une fois que vous démarrez pour la première fois Skype pour les entreprises et Outlook.
  
- Création d’un groupe de sécurité et d’ajout des autorisations de délégation pour ce groupe de sécurité n’est pas pris en charge.
    
- MAPI n’est pas disponible. Voir [l’Erreur « MAPI non disponible » dans Skype pour client d’entreprise 2016](https://support.microsoft.com/en-us/help/3147130).
    
- La boîte aux lettres Exchange Online n’est pas accessible via le Skype pour client d’entreprise. Si cela se produit, exécuter le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) afin de vous assurer qu’il passe.
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 