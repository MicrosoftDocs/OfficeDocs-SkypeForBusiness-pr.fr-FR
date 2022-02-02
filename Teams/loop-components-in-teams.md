---
title: Vue d’ensemble des composants Loop dans Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment gérer les composants Loop dans Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a43ea4c217e09ad4473513fd21e159bd15c89716
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312446"
---
# <a name="overview-of-loop-components-in-teams"></a>Vue d’ensemble des composants Loop dans Teams

Les composants en boucle Teams conversation instantanée offrent une nouvelle façon de donner une idée, de créer et de prendre des décisions ensemble. Envoyez un composant (tableau, liste de tâches ou paragraphe) dans lequel chaque personne de votre conversation peut modifier le texte et voir les modifications à mesure qu’elle est apportée. 

> [!Note]
> Les composants Loop sont la première fonctionnalité de [l’application Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) disponible dans Teams. 

**Accomplir des tâches plus rapidement ensemble.** Sourcez un ordre du jour, suivez les éléments d’action d’un groupe ou prenez des notes collectivement. Voici quelques scénarios simples à simplifier avec les composants Loop.

**Partager des composants.** Dans cette version, vous pouvez partager les composants Loop dans différentes Teams conversations. Les destinataires peuvent apporter des modifications où qu’ils soient et voir instantanément les mises à jour, quel que soit l’endroit où ont été apportées les modifications.

**Démarrez la conversation, créez à partir de là.** Chaque composant que vous créez à partir Teams conversation est automatiquement enregistré dans un fichier dans OneDrive. Par exemple, vous pouvez commencer à collaborer dans une conversation, puis vous déplacer plus tard vers le fichier, où vous avez un espace visuel plus grand pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur Teams applications sur Windows, Mac, Linux, iOS et Android.

## <a name="loop-components-and-fluid-files"></a>Composants de boucle et fichiers .fluid

Les composants de boucle créés Teams sont dosés par un fichier .fluid stocké dans le fichier OneDrive. Le fait d’être un fichier OneDrive signifie que les utilisateurs peuvent créer, découvrir et gérer des composants Loop (fichiers .fluid) aussi facilement que n’importe quel document Office document. Les fichiers .fluid fonctionnent avec les fonctionnalités de gouvernance des données telles que la découverte électronique, l’audit, les rapports et la gestion des droits.

## <a name="how-are-fluid--files-stored"></a>Comment sont stockés les fichiers .fluid ?

Les fichiers .fluid apparaissent sur Office.com et OneDrive, par exemple dans les zones récents et recommandés. Les utilisateurs peuvent rechercher du contenu dans des fichiers .fluid depuis Office.com et OneDrive. Les fichiers .fluid peuvent être restaurés vers des versions antérieures à partir de OneDrive. Pour créer des composants loop, les participants à la conversation doivent avoir un OneDrive compte. Sans compte OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs qui possèdent un compte OneDrive valide, mais ne peuvent pas créer leur propre compte. 

Le déplacement d’un fichier .fluid à partir OneDrive vers un site SharePoint entraînera l’échec du chargement du composant dynamique dans Teams conversation.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?

OneDrive stratégies de rétention s’appliquent aux fichiers .fluid comme aux autres contenus créés par l’utilisateur.

## <a name="how-are-fluid-files-shared"></a>Comment les fichiers .fluid sont-ils partagés ?

Les composants de boucle peuvent être insérés dans Teams conversation ou copiés d’une conversation à l’autre. (Les composants de boucle ne sont pas encore pris en charge dans les canaux.) Elles utilisent par défaut les autorisations existantes de l’organisation, mais les utilisateurs peuvent modifier les autorisations avant l’envoi pour s’assurer que tout le monde y a accès.

L’ouverture de composants à partir Teams conversation dans Office.com propose des fonctionnalités de partage en haut de la fenêtre, similaires aux options de partage proposées pour d’Office documents.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Que se passe-t-il si un fichier .fluid est endommagé ?

L’historique des versions vous permet de passer en revue et de copier des versions précédentes du fichier.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quelles applications peuvent ouvrir et modifier des fichiers .fluid ?

Les fichiers .fluid peuvent uniquement être ouverts en tant que liens dans votre navigateur, comme Office.com, et en tant que composants Loop dans Teams conversation. Si elles sont téléchargées, elles ne peuvent pas être ouvertes à nouveau sans les avoir téléchargées au départ vers OneDrive ou SharePoint.

## <a name="known-issues"></a>Problèmes connus

- Les composants de boucle dans la conversation ne peuvent pas être modifiés via application Office’utilisation Teams sur Android.
- Si les autorisations de fichier par défaut du client sont définies sur Personnes spécifiques *(seules* les personnes spécifiées par l’utilisateur) et  que l’expéditeur supprime des utilisateurs de la liste Des personnes spécifiques dans la boîte de dialogue Autorisations lors de la création d’un composant, ces utilisateurs peuvent encore avoir accès au contenu.
- Avec les autorisations de fichier par défaut du client définies sur Personnes spécifiques *(* seules les personnes spécifiées par l’utilisateur), copier le lien pour le composant live et coller dans une autre conversation nécessite que l’expéditeur utilise la boîte de dialogue Autorisations et ajoute les destinataires dans l’option Personnes spécifiques pour accorder l’accès correctement.
- Avec les autorisations de fichier par défaut du client définies sur Personnes spécifiques *(* seules les personnes spécifiées par l’utilisateur), la création d’un composant en direct dans la conversation de groupe de plus de 20 membres nécessite que l’expéditeur sélectionne manuellement les options d’autorisation pour le composant.
- La recherche de composants Loop dans Teams recherche a pour effet de renvoyer un lien vers le composant dans office.com et non le message de conversation proprement dit.
- Les composants de boucle sont désactivés dans les conversations fédérées.
- Les invités B2B ne pourront pas collaborer sur un composant en direct partagé avec *eux via des* liens vers des personnes de votre organisation, sauf si le client définit une option d’accès externe pour autoriser les invités B2B à avoir le même niveau d’accès que les membres du client. Pour plus d’informations, [voir Configurer les paramètres de collaboration externe B2B](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings).
- Les composants de boucle ne sont pas pris en charge Teams canaux.
- Les composants de boucle dans la conversation ne se chargeront pas uniquement si le fichier a été déplacé vers une autre bibliothèque. Si le fichier est déplacé vers un autre dossier, il continuera à être chargé dans la conversation.
