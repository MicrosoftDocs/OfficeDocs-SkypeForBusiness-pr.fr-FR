---
title: Vue d’ensemble des composants de boucle dans Teams
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
description: Découvrez comment gérer les composants de boucle dans Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e0b9c5a7ffef07a1d9245d2b1266a071b4ee0c2
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795053"
---
# <a name="overview-of-loop-components-in-teams"></a>Vue d’ensemble des composants de boucle dans Teams

Les composants de boucle dans la conversation Teams offrent un nouveau moyen d’imaginer, de créer et de prendre des décisions ensemble. Envoyez un composant ( tel qu’une table, une liste de tâches ou un paragraphe ) dans lequel tous les utilisateurs de votre conversation peuvent modifier en ligne et voir les modifications à mesure qu’elles sont apportées. 

> [!Note]
> Les composants de boucle sont la première fonctionnalité de [l’application Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) à être disponible dans Teams. 

**Effectuez des tâches plus rapidement ensemble.** Sourcez un ordre du jour, suivez les éléments d’action d’un groupe ou prenez des notes collectivement. Il ne s’agit que de quelques scénarios facilités avec les composants de boucle.

**Partagez des composants.** Dans cette version, vous pouvez partager des composants de boucle dans différentes conversations Teams. Les destinataires peuvent modifier où qu’ils se trouvent et voir instantanément les mises à jour, quel que soit l’endroit où les modifications ont été apportées.

**Commencez dans la conversation, générez à partir de là.** Chaque composant que vous créez à partir d’une conversation Teams est automatiquement enregistré dans un fichier dans OneDrive. Par conséquent, vous pouvez commencer à collaborer dans la conversation, puis passer ultérieurement au fichier sur Office.com, où vous disposez d’un plus grand espace visuel pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

Pour plus d’informations sur les paramètres d’administration des composants de boucle dans Teams, consultez [Gérer les composants de boucle dans SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur les applications Teams sur Windows, Mac, Linux, iOS et Android.

## <a name="loop-components-and-fluid-files"></a>Composants de boucle et fichiers .fluid

Les composants de boucle créés dans Teams sont soutenus par un fichier .fluid (qui sera bientôt remplacé par .loop) stocké dans oneDrive du créateur. Le fait d’être un fichier dans OneDrive signifie que les utilisateurs peuvent créer, découvrir et gérer des composants de boucle (fichiers .fluid) aussi facilement que n’importe quel document Office. 

## <a name="how-are-fluid-files-stored"></a>Comment les fichiers .fluid sont-ils stockés ?

Les fichiers .fluid apparaissent sur Office.com et OneDrive, par exemple dans les zones Récentes et Recommandées. Les utilisateurs peuvent rechercher du contenu dans des fichiers .fluid à partir de Office.com et OneDrive. Les fichiers .fluid peuvent être restaurés vers des versions précédentes à partir de OneDrive. Pour créer des composants de boucle, les participants à la conversation doivent disposer d’un compte OneDrive. Sans compte OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs qui ont un compte OneDrive valide, mais qui ne peuvent pas créer le leur. 

Le déplacement d’un fichier .fluid de OneDrive vers un site SharePoint entraîne l’échec du chargement du composant en direct dans la conversation Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?

Les stratégies de rétention OneDrive s’appliquent aux fichiers .fluid comme elles le font pour d’autres contenus créés par l’utilisateur.

## <a name="how-are-fluid-files-shared"></a>Comment les fichiers .fluid sont-ils partagés ?

Les composants de boucle peuvent être insérés dans la conversation Teams ou copiés d’une conversation à une autre. (Les composants de boucle ne sont pas encore pris en charge dans les canaux.) Ils sont par défaut les autorisations existantes de l’organisation, mais les utilisateurs peuvent modifier les autorisations avant de les envoyer pour s’assurer que tout le monde a accès.

L’ouverture des composants de la conversation Teams dans Office.com offre des fonctionnalités de partage en haut de la fenêtre, comme les options de partage offertes pour d’autres documents Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Que se passe-t-il si un fichier .fluid est endommagé ou endommagé ?

L’historique des versions vous permet d’examiner, de restaurer ou de copier à partir des versions précédentes du fichier.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quelles applications peuvent ouvrir et modifier des fichiers .fluid ?

Les fichiers .fluid ne peuvent être ouverts qu’en tant que liens dans votre navigateur, tels que Office.com, et en tant que composants de boucle dans la conversation Teams. S’ils sont téléchargés, ils ne peuvent pas être rouverts sans les télécharger d’abord sur OneDrive ou SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Les fichiers .fluid prennent-ils en charge eDiscovery ?

Les fichiers .fluid sont détectables, mais ont une prise en charge limitée du flux de travail eDiscovery. Actuellement, les fichiers .fluid sont stockés dans le OneDrive du créateur et sont disponibles pour la recherche et la collecte dans eDiscovery (Standard) et eDiscovery (Premium). Toutefois, ils ne s’affichent pas en préversion et le format d’exportation pour révision n’est pas consommable par les outils existants. Pour afficher le contenu exporté, chargez-le sur n’importe quel OneDrive. Si vous le souhaitez, vous pouvez désactiver temporairement ces expériences comme indiqué dans la section [Gestion des paramètres](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Si la boucle est désactivée à partir du commutateur d’administration, quelle sera l’expérience utilisateur ?

Si vous désactivez ces expériences comme indiqué dans la section [Gestion des paramètres](/sharepoint/manage-loop-components#settings-management) , les modifications d’expérience suivantes s’appliquent :

- Le point d’entrée de création/insertion dans la messagerie Teams est masqué. Les utilisateurs ne pourront pas créer de fichiers .fluid.
- Les messages existants qui auraient été rendus sous la forme d’un composant de boucle interactive s’affichent à la place sous la forme d’un lien hypertexte « Composant de boucle ». Aucun contenu interactif n’est affiché dans Teams.
- Lorsqu’un utilisateur final clique sur le lien hypertexte « Composant de boucle » ou accède à un fichier .fluid dans OneDrive Entreprise et clique pour l’ouvrir, il ouvre le fichier dans un onglet de navigateur distinct. Les utilisateurs finaux peuvent toujours modifier le fichier.

## <a name="known-issues"></a>Problèmes connus

- Avec les autorisations de fichier par défaut du locataire définies sur *Des personnes spécifiques* (seules les personnes spécifiées par l’utilisateur), la copie du lien vers le composant Loop et son collage dans une autre conversation nécessitent que l’expéditeur utilise la boîte de dialogue Autorisations et ajoute les destinataires dans l’option Personnes spécifiques pour accorder l’accès correctement.
- Avec les autorisations de fichier par défaut du locataire définies sur *Des personnes spécifiques* (seules les personnes spécifiées par l’utilisateur), la création d’un composant en direct dans une conversation de groupe avec plus de 20 membres nécessite que l’expéditeur sélectionne manuellement les options d’autorisation pour le composant.
- La recherche de composants de boucle dans la recherche Teams renvoie un lien vers le composant dans office.com, et non le message de conversation lui-même.
- Les composants de boucle sont désactivés dans les conversations fédérées.
- Les invités ne pourront pas collaborer sur un composant en direct partagé avec eux via Company Share Link. Définissez des autorisations pour **Personnes actuellement dans cette conversation** pour partager des composants avec des invités.
- Les composants de boucle ne sont pas pris en charge dans les canaux Teams.
- Les composants de boucle dans la conversation ne se chargent pas uniquement si le fichier a été déplacé vers une bibliothèque différente. Si le fichier est déplacé vers un autre dossier, il continue à se charger dans la conversation.
