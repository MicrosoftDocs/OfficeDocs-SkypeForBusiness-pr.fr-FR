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
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1405464a3eb963d55c357b5fcc165c67a143e5e1
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198546"
---
# <a name="overview-of-loop-components-in-teams"></a>Vue d’ensemble des composants de boucle dans Teams

Les composants de boucle dans la conversation Teams offrent une nouvelle façon de créer des idées, de créer et de prendre des décisions ensemble. Envoyez un composant , comme un tableau, une liste de tâches ou un paragraphe, dans lequel tous les participants à votre conversation peuvent modifier inline et voir les modifications au fur et à mesure qu’elles sont apportées. 

> [!Note]
> Les composants de boucle sont la première fonctionnalité de [l’application Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) disponible dans Teams. 

**Effectuez des tâches plus rapidement ensemble.** Créer un ordre du jour, suivre les actions d’un groupe ou prendre des notes collectivement. Il ne s’agit que de quelques scénarios simplifiés avec les composants loop.

**Partager des composants.** Dans cette version, vous pouvez partager des composants loop dans différentes conversations Teams. Les destinataires peuvent modifier où qu’ils se trouvent et voir les mises à jour instantanément, quel que soit l’emplacement où les modifications ont été apportées.

**Démarrez dans la conversation, générez à partir de là.** Chaque composant que vous créez à partir d’une conversation Teams est automatiquement enregistré dans un fichier dans OneDrive. Par conséquent, vous pouvez commencer à collaborer dans la conversation, puis passer au fichier sur Office.com, où vous disposez d’un espace visuel plus grand pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

Pour plus d’informations sur les paramètres d’administration des composants de boucle dans Teams, voir [Gérer les composants de boucle dans SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur les applications Teams sur Windows, Mac, Linux, iOS et Android.

## <a name="loop-components-and-fluid-files"></a>Composants de boucle et fichiers .fluid

Les composants de boucle créés dans Teams sont soutenus par un fichier .fluid (qui sera remplacé par .loop dans un avenir proche) stocké dans le OneDrive du créateur. Le fait d’être un fichier dans OneDrive signifie que les utilisateurs peuvent créer, découvrir et gérer des composants de boucle (fichiers .fluid) aussi facilement que n’importe quel document Office. 

## <a name="how-are-fluid-files-stored"></a>Comment les fichiers .fluid sont-ils stockés ?

Les fichiers .fluid apparaissent sur Office.com et OneDrive, par exemple dans les zones Récents et Recommandés. Les utilisateurs peuvent rechercher du contenu dans des fichiers .fluid à partir de Office.com et OneDrive. Les fichiers .fluid peuvent être restaurés dans des versions antérieures à partir de OneDrive. Pour créer des composants de boucle, les participants doivent disposer d’un compte OneDrive. Sans compte OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs disposant d’un compte OneDrive valide, mais ne peuvent pas créer le leur. 

Le déplacement d’un fichier .fluid de OneDrive vers un site SharePoint entraîne l’échec du chargement du composant actif dans la conversation Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?

Les stratégies de rétention OneDrive s’appliquent aux fichiers .fluid tout comme à d’autres contenus créés par l’utilisateur.

## <a name="how-are-fluid-files-shared"></a>Comment les fichiers .fluid sont-ils partagés ?

Les composants de boucle peuvent être insérés dans la conversation Teams ou copiés d’une conversation à l’autre. (Les composants de boucle ne sont pas encore pris en charge dans les canaux.) Ils mettent par défaut les autorisations existantes de l’organisation, mais les utilisateurs peuvent modifier les autorisations avant l’envoi pour s’assurer que tout le monde y a accès.

L’ouverture de composants à partir d’une conversation Teams dans Office.com offre des fonctionnalités de partage en haut de la fenêtre, similaires aux options de partage proposées pour d’autres documents Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Que se passe-t-il si un fichier .fluid est endommagé ou endommagé ?

L’historique des versions vous permet d’examiner, de restaurer ou de copier des versions précédentes du fichier.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quelles applications peuvent ouvrir et modifier des fichiers .fluid ?

Les fichiers .fluid peuvent uniquement être ouverts sous forme de liens dans votre navigateur, tels que Office.com, et en tant que composants de boucle dans la conversation Teams. S’ils sont téléchargés, ils ne peuvent pas être rouverts sans les avoir téléchargés au préalable sur OneDrive ou SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Les fichiers .fluid prennent-ils en charge eDiscovery ?

Les fichiers .fluid sont détectables, mais ont une prise en charge limitée du flux de travail eDiscovery. Actuellement, les fichiers .fluid sont stockés dans le OneDrive du créateur et sont disponibles pour la recherche et la collecte dans eDiscovery (Standard) et eDiscovery (Premium). Toutefois, ils ne s’affichent pas en préversion et le format d’exportation pour révision n’est pas consommable par les outils existants. Pour afficher le contenu exporté, chargez-les sur n’importe quel OneDrive. Si vous le souhaitez, vous pouvez désactiver temporairement ces expériences comme indiqué dans la section [Gestion des paramètres](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Si loop est désactivé à partir du commutateur administrateur, quelle sera l’expérience utilisateur ?

Si vous désactivez ces expériences comme indiqué dans la section [Gestion des paramètres](/sharepoint/manage-loop-components#settings-management) , les modifications d’expérience suivantes s’appliquent :

- Le point d’entrée de création/d’insertion dans la messagerie Teams est masqué. Les utilisateurs ne pourront pas créer de fichiers .fluid.
- Les messages existants qui auraient précédemment été rendus en tant que composant de boucle interactive s’affichent sous la forme d’un lien hypertexte « composant de boucle ». Aucun contenu interactif n’est affiché dans Teams.
- Lorsqu’un utilisateur final clique sur le lien hypertexte « Composant de boucle » ou accède à un fichier .fluid dans OneDrive Entreprise et clique pour l’ouvrir, il ouvre le fichier dans un onglet de navigateur distinct. Les utilisateurs finaux pourront toujours modifier le fichier.

## <a name="known-issues"></a>Problèmes connus

- Avec les autorisations de fichier par défaut du locataire définies sur *Personnes spécifiques* (uniquement les personnes spécifiées par l’utilisateur), pour copier le lien vers le composant Boucle et le coller dans une autre conversation, l’expéditeur doit utiliser la boîte de dialogue d’autorisations et ajouter les destinataires dans l’option Personnes spécifiques pour accorder l’accès correctement.
- Avec les autorisations de fichier par défaut du locataire définies sur *Personnes spécifiques* (uniquement les personnes spécifiées par l’utilisateur), la création d’un composant en direct dans une conversation de groupe avec plus de 20 membres nécessite que l’expéditeur sélectionne manuellement les options d’autorisation pour le composant.
- La recherche de composants de boucle dans la recherche Teams renvoie un lien vers le composant dans office.com, et non le message de conversation proprement dit.
- Les composants de boucle sont désactivés dans les conversations fédérées.
- Les invités ne pourront pas collaborer sur un composant en direct qui est partagé avec eux via le lien de partage d’entreprise. Définissez des autorisations pour **Personnes actuellement dans cette conversation** pour partager des composants avec des invités.
- Les composants de boucle ne sont pas pris en charge dans les canaux Teams.
- Les composants de boucle dans la conversation ne se chargent pas uniquement si le fichier a été déplacé vers une autre bibliothèque. Si le fichier est déplacé vers un autre dossier, il continuera à se charger dans la conversation.
