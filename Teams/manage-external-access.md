---
title: Gérez l’accès externe (fédération) dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Votre administrateur informatique peut configurer l’accès externe pour d’autres domaines (fédération) permettre aux utilisateurs de ces domaines de participer à des équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b04b125f5cb998c71f161bf31809a39097accf6c
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955021"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Gérez l’accès externe (fédération) dans Microsoft Teams
======================================================

Avec un accès externe Teams Microsoft, les utilisateurs d’autres domaines peuvent participer à vos conversations et les appels. Vous pouvez également autoriser les utilisateurs externes qui sont toujours à l’aide Skype pour les entreprises à participer. 

Accès externe (fédération) et l’accès invité sont différentes :

- Accès invité donne l’autorisation d’accès à une seule personne. Accès externe donne l’autorisation d’accès à la totalité d’un domaine.

- Accès invité, une fois accordé par le propriétaire de l’équipe, autorise invité à [accéder aux ressources](guest-experience.md), telles que les discussions sur le canal et les fichiers, pour une équipe spécifique et conversation avec d’autres utilisateurs de l’équipe qu’ils ont été invités à. Avec un accès externe (conversation fédérée), les participants à la conversation externes n’ont accès à des équipes ou des ressources de l’équipe de l’organisation à inviter. Ils peuvent participer qu’à une conversation fédérée en tête-à-tête. Administrateurs du client peut choisir entre les options de deux communication selon le niveau de la collaboration est souhaitable avec la partie externe. Administrateurs peuvent choisir approches ou les deux, en fonction de leurs besoins en matière d’organisation, mais il est recommandé d’activation de l’accès invité pour une expérience d’équipes be, collaboration. 

Consultez la table pour une comparaison d’externes et les invités d’accéder aux fonctionnalités suivantes.

| Fonctionnalité | Utilisateurs de l’accès externe | Utilisateurs de l’accès invité |
|---------|-----------------------|--------------------|
| Utilisateur peut converser avec une personne dans une autre société | Oui |Oui  |
| L’utilisateur peut appeler une personne dans une autre société | Oui | Oui  |
| Les utilisateurs peuvent afficher si une personne à partir d’une autre société est disponible pour un appel ou une conversation | Oui | Oui<sup>1</sup> |
| Utilisateur peut rechercher des utilisateurs dans les clients externes | Oui<sup>2</sup> | Non |
| Utilisateur peut partager des fichiers | Non | Oui |
| Utilisateur peut accéder aux ressources d’équipes | Non | Oui |
| Utilisateur peut être ajouté à une conversation de groupe | Non | Oui |
| Utilisateur peut être ajouté à une réunion | Oui | Oui  |
| Utilisateurs supplémentaires peuvent être ajoutés à une conversation avec un utilisateur externe | Aucun<sup>3</sup> | N/A |
| Utilisateur est identifié comme une partie externe | Oui | Oui  |
| Affichage de la présence | Oui | Oui  |
| Absent message s’affiche. | Non | Oui |
| Les utilisateurs individuels peuvent être bloquées. | Non | Oui |
| @mentions sont pris en charge | Non | Oui |
||||

<sup>1</sup> à condition que l’utilisateur a été ajouté en tant qu’invité et est connecté en tant qu’invité au client d’invité.<br>
<sup>2</sup> uniquement par courrier électronique ou l’adresse de protocole SIP (Session Initiation).<br>
<sup>3</sup> conversation (fédérée) externe est 1:1.

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>Activer ou désactiver l’accès externe (les utilisateurs peuvent communiquer avec Skype pour les utilisateurs professionnels et les équipes)

Vous pouvez utiliser la & Microsoft Teams Skype entreprise centre d’administration pour gérer l’accès externe.

1. Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.

     ![Capture d’écran de l’accès externe de paramètres à l’échelle de l’organisation](media/manage-external-access-1.png).

2. Basculez **les utilisateurs peuvent communiquer avec Skype pour les utilisateurs professionnels et les équipes** **activé** ou **désactivé**.

     ![Capture d’écran de l’option d’accès externe est activée](media/manage-external-access-2.png).

3. Cliquez sur **Enregistrer**. 

## <a name="add-or-block-a-domain"></a>Ajouter ou bloquer un domaine

Suivez ces étapes pour ajouter un domaine ou de désactiver l’accès externe pour un domaine.

1. Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.

2. Sélectionnez **Ajouter un domaine**. 
 
    ![Capture d’écran externe page d’accès aux ajouter un lien de domaine](media/manage-external-access-3.png).

   Le volet **Ajouter un domaine** apparaît.

    ![Capture d’écran d’ajouter un volet de domaine](media/manage-external-access-4.png).


3. Sous **Ajouter un domaine**, tapez le nom du domaine ; par exemple, tapez Contoso.com.

4. Sélectionnez **autorisées** ou **bloquées**. Vous pouvez modifier ce paramètre à tout moment.

2. Cliquez sur **terminé**.

Après avoir ajouté un domaine, vous verrez le nom de domaine et l’état ajouté à la liste des domaines dans la page d’accès externe.

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur l’accès invité dans Microsoft Teams, voir [Gérer les accès invité dans les équipes Microsoft](manage-guests.md).