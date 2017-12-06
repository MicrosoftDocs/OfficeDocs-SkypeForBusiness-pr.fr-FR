---
title: "Configurer et dépanner Skype pour la délégation entreprise Online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/23/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
description: "Cet article explique comment configurer et dépanner Skype pour la délégation entreprise Online. Cet article vous donne des conseils pour les recommandations de configuration, les meilleures pratiques et les étapes de dépannage."
---

# Configurer et dépanner Skype pour la délégation entreprise Online

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](e676b911-5f82-41d8-b4ce-3d0d45c3cd04.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/e676b911-5f82-41d8-b4ce-3d0d45c3cd04). 
  
Cet article explique comment configurer et dépanner Skype pour la délégation entreprise Online. Cet article vous donne des conseils pour les recommandations de configuration, les meilleures pratiques et les étapes de dépannage.
  
## Instructions et configuration requise

### Instructions pour la délégation

La configuration et la prise de délégation fonctionne correctement varie selon que vous les recommandations suivantes :
  
- Vous devez utiliser le Skype entreprise 2015 complète client avec les dernières mises à jour ou la Skype entreprise 2016 complète client.
    
- Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.
    
- Assurez-vous que la personne qui a délégué et ordinateurs délégué ont un profil de messagerie Outlook qui est le principal ou le profil par défaut. Ce profil de messagerie doit contenir qu'un seul compte.
    
- Skype entreprise pour la personne qui a délégué et le délégué doit être utilisateurs en ligne. En outre, les boîtes aux lettres Exchange Server pour chaque compte doit être en ligne ou tous deux être en local.
    
- La personne qui a délégué et le délégué doivent être à l'aide de la même version principale d'Outlook.
    
- La valeur d'attribut **EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie client. Vous pouvez vérifier ce paramètre en exécutant l'applet de commande **Get-CSClientPolicy** dans le Skype entreprise Online PowerShell module.
    
- La personne qui a délégué et le délégué doivent être connectés à Skype entreprise et Outlook en même temps sur différents postes de travail.
    
- Boîtes aux lettres partagées ne sont pas pris en charge pour Skype entreprise Online délégation. C'est parce que la boîte aux lettres partagée n'a pas la liste de contrôle d'accès **sendonbehalf** (et).
    
### Skype pour la prise en charge de la version entreprise client

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype entreprise simple**|
|:-----|
|**Skype Entreprise 2015**|
|:-----|
|**Skype Entreprise 2016**|
|:-----|
   
### Conditions de licence

**Scénario de licence entreprise E3**

|****Licence****|****Clients****|****Remarques****|
|:-----|:-----|:-----|
|Entreprise E3  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 entreprise utilisée avec Outlook 2013 ou Outlook 2016  <br/> |Skype entreprise base client non prises en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas dans les réunions.  <br/> |
|Entreprise E3 avec Office 365 téléphone système + xCalling Office 365 Plan  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 entreprise utilisée avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype entreprise base client non prises en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas dans les réunions.  <br/> |
   
**Scénario de licence entreprise E5**

|****Licence****|****Clients****|****Remarques****|
|:-----|:-----|:-----|
|Entreprise E5  <br/> |Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016.  <br/> Skype pour 2016 entreprise utilisée avec Outlook 2013 ou Outlook 2016  <br/> |Skype entreprise base client non prises en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas dans les réunions.  <br/> |
|Entreprise E5 plus offre Office 365 pour appeler  <br/> |Skype entreprise pour Mac 2016  <br/> Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016  <br/> Skype pour 2016 entreprise utilisée avec Outlook 2013 ou Outlook 2016  <br/> Lync pour Mac 2011  <br/> |Skype entreprise base client non prises en charge la délégation.  <br/> Pour les clients Mac, vous pouvez déléguer des appels, mais pas dans les réunions.  <br/> |
   
## Configurer et vérifier la délégation

Pour configurer Skype pour la délégation entreprise Online, procédez comme suit :
  
### Pour les clients Windows

 **Onglet de transfert d'appel**
  
1. Sélectionnez **Outils** > **Options** > **paramètres de transfert d'appel**.
    
2. Sélectionnez **Modifier mes membres délégués**.
    
3. Sélectionnez **Ajouter**, sélectionnez le délégué que vous souhaitez ajouter, puis **OK**.
    
 **Aucun onglet transfert d'appel**
  
1. Dans Outlook, sélectionnez **fichier** > **Paramètres du compte** > **Accès délégué** > **Ajouter**.
    
2. Recherchez et ajoutez le nom de la personne qui va agir en tant que délégué.
    
3. Sélectionnez le menu **calendrier**, puis **éditeur (peut lire, créer et modifier des éléments)**.
    
### Pour les clients Mac - Lync

 **Onglet de transfert d'appel**
  
- Si le client ne possède un onglet de **Transfert d'appel** dont le lien **Modifier mes membres délégués** et que la personne qui a délégué se trouve sur un ordinateur Mac, la personne qui a délégué doit se connecter à un ordinateur fonctionnant sous Windows afin de configurer la délégation. C'est parce que les clients Mac ne peut pas faire connexions MAPI, et il s'agit d'une obligation d'établir Skype pour la délégation d'entreprise à partir d'Outlook.
    
### Vérification de réussite

Si le programme d'installation a réussi, le délégué doit voir que **vous avez été ajouté en tant que délégué pour < nom >** message et que la **personne dont je gère les appels** création du groupe. La personne qui a délégué doit s'afficher que le groupe **délégués** est créé.
  
> [!NOTE]
> Autorisations de délégation s'affichent généralement dans les 30 minutes au processus d'installation. Toutefois, ce processus peut prendre jusqu'à 24 heures. 
  
## Résolution des problèmes

### Problèmes courants

> **Problème 1** L'entrée de délégué continue à apparaître dans le groupe **personne dont je gère les appels** après que la personne qui a délégué a supprimé le délégué à partir du client Outlook.
    
    **Solution 1** Dans Skype entreprise, cliquez sur le délégué dans le groupe **délégués** et puis sélectionnez **Supprimer du groupe**.
    
> **Problème 2** Une fois l'accès délégué est accordé via le client Outlook, le groupe **personne dont je gère les appels** ni le message de confirmation s'affichent pour le délégué.
    
    **Résolution 2** Supprimer la délégation à partir du client Outlook, patientez environ 15 minutes pour la réplication, et ajoutez à nouveau le délégué.
    
### Autres problèmes courants

- Délégation ne fonctionne pas si le seuil de 25 personnes qui délèguent et 25 délégués est dépassé.
    
- La Skype entreprise base client n'est pas pris en charge.
    
    > [!NOTE]
    > Si vous installez la Skype entreprise base client, il vous sera supprimer et rompre délégation. 
  
- Si la valeur **Status MAPI** n'est pas **OK**, assurez-vous que les valeurs **SIP** et **SMTP** correspondent.
    
    > [!NOTE]
    > Il peut prendre plusieurs minutes pour que le statut MAPI à afficher en tant que **OK** une fois que vous commencez Skype entreprise et Outlook.
  
- Création d'un groupe de sécurité et en ajoutant des autorisations de délégation pour ce groupe de sécurité n'est pas pris en charge.
    
- MAPI n'est pas disponible. Voir [Erreur « MAPI non disponible » dans Skype entreprise 2016 client](https://support.microsoft.com/en-us/help/3147130).
    
- La boîte aux lettres Exchange Online n'est pas accessible par le biais du Skype entreprise. Si cela se produit, exécutez le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) pour vous assurer qu'il passe.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

