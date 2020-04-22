---
title: À quoi ressemble l'expérience des invités
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Découvrez la fonctionnalité Microsoft Teams disponible pour les utilisateurs invités.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60891c2e5283b8e9cdaa9e8d7852768bbb52d8aa
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776929"
---
<a name="what-the-guest-experience-is-like"></a>À quoi ressemble l'expérience des invités
=================================

Lorsqu’un invité est invité à rejoindre une équipe, il reçoit un message électronique de bienvenue. Ce message inclut des informations sur l’équipe et ce à quoi vous devez vous attendre. L’invité doit accepter l’invitation en sélectionnant **Ouvrir Microsoft teams** dans le message électronique avant de pouvoir accéder à l’équipe et à ses canaux.
    
![Capture d’écran montrant un exemple de message électronique de bienvenue](media/guest-experience-image1.png)
    
Tous les membres de l'équipe voient un message dans le fil des canaux informant que le propriétaire de l'équipe a ajouté un invité et indiquant son nom. Tous les membres de l'équipe peuvent identifier facilement les utilisateurs qui sont invités. Comme le montre la capture d’écran d’un exemple d’équipe, une bannière indique « cette équipe a des invités » et une étiquette **(invité)** apparaît en regard du nom de chaque invité.
    
![Capture d’écran illustrant des notifications de bannière aux utilisateurs invités](media/guest-experience-image2.png "La capture d’écran montre une partie du canal marketing de Northwind Traders, avec la notification dans la bannière supérieure indiquant que l’équipe a des invités et des utilisateurs identifiés par le mot « GUEST » à côté de leur nom.")

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparaison entre le membre d’équipe et les fonctionnalités d’invité

Le tableau suivant compare les fonctionnalités d’équipes disponibles pour les membres de l’équipe d’une organisation et ses invités.

|**Fonctionnalité dans Teams**|**Utilisateur de Teams dans l'organisation**|**Utilisateur invité**|
|:-----|:-----|:-----|
|Créer un canal  <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation privée  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation dans un canal  <br/> |&#x2713;|&#x2713;|
|Publier, supprimer et modifier des messages  <br/> |&#x2713;|&#x2713;|
|Partager un fichier dans un canal  <br/> |&#x2713;|&#x2713;|
|Partager un fichier dans une conversation  <br/> |&#x2713;||
|Ajouter des applications (onglets, bots ou connecteurs)  <br/> |&#x2713;||
|Créer des réunions ou des échéanciers d’accès  <br/> |&#x2713;||
|Accès au stockage OneDrive entreprise  <br/> |&#x2713;||
|Créer des stratégies d'accès invité qui s'appliquent à l'ensemble du client et aux équipes/canaux  <br/> |&#x2713;||
|Inviter un utilisateur en dehors du domaine de l’organisation 365 Office <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> <br/> |&#x2713;||
|Créer une équipe  <br/> |&#x2713;||
|Rechercher et rejoindre une équipe publique  <br/> |&#x2713;||
|Afficher l'organigramme  <br/> |&#x2713;||
|Utiliser la traduction intraligne  <br/> |&#x2713;||
|Devenir le propriétaire de l’équipe  <br/> |&#x2713;||

   
Le tableau suivant répertorie les fonctionnalités d’appel et de réunion accessibles aux invités par rapport aux autres types d’utilisateurs.

| Fonction d’appel | Dactylo | Utilisateurs E1 et E3 | E5 et utilisateur voix entreprise |
| --------------- | ----- | -------------- | -------------- |
| Appels VOIP | Oui | Oui  | Oui  |
| Appels de groupe | Oui | Oui  | Oui  |
| Commandes d’appel principales prises en charge (mise en attente, muet, vidéo activées, partage d’écran) | Oui | Oui  | Oui  |
| Destination du transfert | Oui | Oui  | Oui  |
| Peut transférer un appel | Oui | Oui  | Oui  |
| Possibilité de transférer des conseils | Oui | Oui  | Oui  |
| Peut ajouter d’autres utilisateurs à un appel via le protocole VOIP | Oui | Oui  | Oui  |
| Peut ajouter des utilisateurs par numéro de téléphone à un appel | Non | Non | Oui |
| Destination directe | Non | Oui | Oui  |
| Cible du groupe d’appels | Non | Oui | Oui  |
| Cible sans réponse | Non | Oui | Oui  |
| Peut être la cible d’un appel fédéré | Non | Oui | Oui  |
| Possibilité d’effectuer un appel fédéré | Non | Oui | Oui  |
| Peut immédiatement transférer ses appels | Non | Non | Oui |
| Peuvent sonner simultanément dans leurs appels | Non | Non | Oui |
| Peut acheminer les appels sans réponse | Non | Non | Oui |
| Les appels en absence peuvent être dirigés vers la boîte vocale | Non | No<sup>1</sup> |Oui |
| Avoir un numéro de téléphone capable de recevoir des appels | Non | Non | Oui |
| Peut composer des numéros de téléphone | Non | Non | Oui |
| Peut accéder aux paramètres de l’appel | Non | Non | Oui |
| Peut changer le message d’accueil de la boîte vocale | Non | No<sup>1</sup> | Oui |
| Possibilité de modifier les sonneries | Non | Non  | Oui |
| Prend en charge TTY | Non | Non | Oui |
| Peuvent avoir des délégués | Non | Non | Oui |
|  Il peut s’agir d’un délégué | Non | Non | Oui |


<sup>1</sup> cette fonction sera disponible prochainement.

> [!NOTE]
> Les administrateurs d'Office 365 contrôlent les fonctionnalités disponibles pour les invités. 

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

### <a name="how-do-i-leave-an-organization-that-ive-been-invited-to"></a>Comment puis-je laisser une organisation à laquelle j’ai été invité ?
Si vous avez été invité à une organisation dont vous ne voulez pas être invité, vous pouvez choisir de quitter l’organisation. Pour plus d’informations, voir [quitter une organisation en tant qu’utilisateur invité](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization). Par ailleurs, vous pouvez demander à l’administrateur de l’organisation de vous supprimer de son locataire. Notez que, dans tous les cas, vous devrez être réinvité pour le client si vous souhaitez accéder à l’organisation ultérieurement.

### <a name="do-guests-have-the-same-capabilities-as-team-members"></a>Les invités ont-ils les mêmes fonctionnalités que les membres de l’équipe ?
Non. Pour plus d’informations sur ce qu’un invité peut et ne peut pas faire, consultez la rubrique [comparaison des fonctionnalités de membre d’équipe et d’invité](#comparison-of-team-member-and-guest-capabilities) dans cet article.

### <a name="do-guests-have-access-to-onedrive-for-business"></a>Les invités peuvent-ils accéder à OneDrive entreprise ?
Non.

### <a name="do-guests-have-access-to-sharepoint-files"></a>Les invités peuvent-ils accéder aux fichiers SharePoint ?
Oui.

### <a name="can-guests-search-within-files"></a>Les invités peuvent-ils effectuer une recherche dans les fichiers ?
Non.

### <a name="can-guests-attach-files"></a>Les invités peuvent-ils joindre des fichiers ?
Oui, un invité peut joindre des fichiers de deux manières :

   - Sélectionnez **fichiers** dans le volet gauche, puis accédez à l’emplacement du fichier.
   - Chargez des fichiers à partir de leur ordinateur.

### <a name="can-a-guest-download-a-file-in-a-private-chat"></a>Un invité peut-il télécharger un fichier dans une conversation privée ?
Oui, il peut recevoir un fichier d’un membre d’une conversation privée, puis le télécharger sur son bureau.
