---
title: "Résolution des problèmes audio de conférence et les problèmes connus"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6

description: "Get a list of known isses when using Microsoft as their dial-in conference provider, status, and some work arounds. "
---

# Résolution des problèmes audio de conférence et les problèmes connus

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
 **Cet article concerne Skype pour les utilisateurs d'entreprise et Teams Microsoft à l'aide de Microsoft en tant que leur fournisseur de services d'audioconférence. Il ne s'applique pas aux clients qui utilisent un fournisseur de services d'audioconférence tiers (ACP).**
  
## Problèmes connus et résolution des problèmes

Mises à jour d'Office 365 de services d'audioconférence qui utilise Microsoft, comme le fournisseur de services d'audioconférence présente des problèmes en cours qui sont suivies et activement examinée et seront potentiellement résolus lorsque la fonctionnalité est mis à jour à l'avenir.
  
Pour l'instant, utilisez la documentation comme référence lorsque vous résolvez des problèmes potentiels liés à l'obtention de configurer les conférences Audio et à l'utilisation pour les personnes qui utilisent le Skype pour les applications d'entreprise ou Microsoft Teams dans votre organisation.
  
### Application permet aux équipes de Microsoft

|**Problème**|**Comportement/symptômes**|**Solution connue**|**Date de la détection**|
|:-----|:-----|:-----|:-----|
|Les appelants PSTN avec la même « De » nombre apparaissent en tant que le même utilisateur dans la liste de la réunion.  <br/> |Lorsque plusieurs appelants PSTN participer à une réunion, et leurs ID d'appelant est masqués sous la forme d'un nombre unique, ils seront affiche-t-il comme un seul appelant dans la liste des participants.  <br/> |Il n'existe aucune solution.  <br/> |9/25/2017  <br/> |
|Panneau informations de réunion n'apparaît pas intermittente.  <br/> |Panneau informations de réunion peut ne pas affiche dans le client équipes lorsque vous essayant d'utilisateurs Rechercher numéros de téléphone de pont de conférence ou ID de conférence.  <br/> |Examiner les détails de la réunion ou un calendrier Outlook pour afficher les numéros de téléphone de pont de conférence ou ID de conférence.  <br/> |9/25/2017  <br/> |
|Invitations aux réunions à partir d'Outlook Add-in affichent des caractères incorrects en coordonnées PSTN pour les paramètres régionaux non-US.  <br/> |Lors de la planification de réunions privées avec Outlook Add-in pour Microsoft Teams sur un ordinateur des paramètres régionaux non-US, PSTN coordonnées peuvent contenir des caractères incorrects.  <br/> |Il n'existe aucune solution.  <br/> |9/25/2017  <br/> |
|Appels sortants doit utiliser au moins 5 chiffres.  <br/> |Les utilisateurs essaient établir une connexion à partir d'une réunion nécessaire de taper en chiffres 5 ou plus, même si la règle de normalisation de plan de numérotation n'est pas disponible pour normaliser chiffres courte à E.164.  <br/> |Appels sortants en tapant son numéro DID complet ou le format de nombre local au lieu de numéro de poste interne.  <br/> |9/25/2017  <br/> |
|Appel sortant contrôle n'apparaît pas intermittente.  <br/> |Appels sortants contrôle ne peuvent pas être visibles à partir du panneau informations sur la réunion.  <br/> |Il n'existe aucune solution.  <br/> |9/25/2017  <br/> |
|ID de conférence statique ne pas pris en charge pour les réunions Teams Microsoft.  <br/> |Si l'administrateur remplace le paramètre par défaut à partir de l'ID de conférence dynamique à l'ID de conférence statique, ce paramètre ne prend effet pour les réunions Teams Microsoft. Voir [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Il n'existe aucune solution.  <br/> |9/25/2017  <br/> |
   
### Skype entreprise App

|**Problème**|**Comportement/symptômes**|**Solution connue**|**Date de la détection**|
|:-----|:-----|:-----|:-----|
|Notifications d'entrée et de sortie sont activées au démarrage d'une réunion, mais qu'ils sont désactivés peu après le début de la réunion.  <br/> |Par défaut, les notifications d'entrée et de sortie sont désactivées pour les réunions dans laquelle participants participer depuis les deux Skype pour les applications métier et quand ils se connectent. Vous pouvez activer les annonces dans les **Options de réunion Skype** dans le Skype entreprise App. Pour une réunion où tous les participants se connectent et participer à une réunion, les notifications d'entrée et de sortie sont activées par défaut que la liste des participants n'est pas disponible pour tous les participants. Lorsque une réunion a démarré avec uniquement les participants dans l'entrée de l'appel et les notifications de fermeture seront activées, mais quand un participant jointures à l'aide d'un Skype entreprise App, les notifications seront désactivés. Lorsque désactivée, les notifications peuvent être activées à l'aide de **Options de réunion Skype** dans le Skype entreprise App. <br/> |Il n'existe aucune solution.  <br/> |8/30/2017  <br/> |
|Si un utilisateur est configuré la première fois par attribué une licence E5, il est possible pour le message électronique de bienvenue audioconférence ne pas être remis à l'utilisateur si la boîte aux lettres n'est pas activée.  <br/> |Dans ce cas, vous pouvez toujours renvoyer les informations de conférence audio de l'utilisateur à l'aide de **conférence Audio** dans la Skype centre d'administration entreprise ou à l'aide de PowerShell. Voir[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).  <br/> > [!NOTE]> Afin de renvoyer les services d'audioconférence code confidentiel à l'utilisateur, le code confidentiel doit être réinitialisé. Cela peut également être exécuté à l'aide de **conférence Audio** dans la Skype centre d'administration entreprise ou à l'aide de PowerShell.          |Il n'existe aucune solution.  <br/> |8/30/2017  <br/> |
|Services d'audioconférence appels peuvent prendre jusqu'à 24 heures pour afficher dans les rapports d'utilisation.  <br/> |Nous cherchons transférer à améliorer cette zone de service futures mises à jour.  <br/> |Il n'existe aucune solution.  <br/> |8/30/2017  <br/> |
|Lorsqu'un appelant appelle un pont de conférence une fois que la réunion a été verrouillée par un utilisateur Skype Entreprise, il n'est pas une notification dans l'application Skype Entreprise indiquant que l'utilisateur se trouve dans la salle d'attente.  <br/> |Cette fonctionnalité est actuellement à l'étude, mais nous avons recueilli les derniers commentaires afin de la mettre en œuvre dans les prochaines mises à jour de service.  <br/> |Il n'existe aucune solution.  <br/> |8/30/2017  <br/> |
   
## Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

