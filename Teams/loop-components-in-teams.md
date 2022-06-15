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
description: Découvrez comment gérer Loop composants dans Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088580"
---
# <a name="overview-of-loop-components-in-teams"></a>Vue d’ensemble des composants Loop dans Teams

Loop composants de Teams conversation offrent une nouvelle façon d’imaginer, de créer et de prendre des décisions ensemble. Envoyez un composant ( tel qu’une table, une liste de tâches ou un paragraphe ) dans lequel tous les utilisateurs de votre conversation peuvent modifier en ligne et voir les modifications à mesure qu’elles sont apportées. 

> [!Note]
> Loop composants est la première fonctionnalité de [l’application Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) à être disponible dans Teams. 

**Effectuez des tâches plus rapidement ensemble.** Sourcez un ordre du jour, suivez les éléments d’action d’un groupe ou prenez des notes collectivement. Ce ne sont là que quelques scénarios facilités avec Loop composants.

**Partagez des composants.** Dans cette version, vous pouvez partager Loop composants dans différentes conversations Teams. Les destinataires peuvent modifier où qu’ils se trouvent et voir instantanément les mises à jour, quel que soit l’endroit où les modifications ont été apportées.

**Commencez dans la conversation, générez à partir de là.** Chaque composant que vous créez à partir de Teams conversation est automatiquement enregistré dans un fichier dans OneDrive. Par conséquent, vous pouvez commencer à collaborer dans la conversation, puis passer ultérieurement au fichier, où vous disposez d’un plus grand espace visuel pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

Pour plus d’informations sur les paramètres d’administration des composants Loop dans Teams, consultez [Gérer les composants Loop dans SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur Teams applications sur Windows, Mac, Linux, iOS et Android.

## <a name="loop-components-and-fluid-files"></a>Loop composants et fichiers .fluid

Loop composants créés dans Teams sont soutenus par un fichier .fluid stocké dans le OneDrive du créateur. Le fait d’être un fichier dans OneDrive signifie que les utilisateurs peuvent créer, découvrir et gérer Loop composants (fichiers .fluid) aussi facilement que n’importe quel document Office. 

## <a name="how-are-fluid--files-stored"></a>Comment les fichiers .fluid sont-ils stockés ?

Les fichiers .fluid apparaissent sur Office.com et OneDrive, par exemple dans les zones Récentes et Recommandées. Les utilisateurs peuvent rechercher du contenu dans des fichiers .fluid à partir de Office.com et OneDrive. Les fichiers .fluid peuvent être restaurés vers des versions antérieures à partir de OneDrive. Pour créer Loop composants, les participants à la conversation doivent disposer d’un compte OneDrive. Sans compte de OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs qui ont un compte OneDrive valide, mais qui ne peuvent pas créer le leur. 

Le déplacement d’un fichier .fluid d’OneDrive vers un site SharePoint entraîne l’échec du chargement du composant en direct dans Teams conversation.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?

OneDrive stratégies de rétention s’appliquent aux fichiers .fluid comme elles le font pour d’autres contenus créés par l’utilisateur.

## <a name="how-are-fluid-files-shared"></a>Comment les fichiers .fluid sont-ils partagés ?

Loop composants peuvent être insérés dans Teams conversation ou copiés d’une conversation à une autre. (Loop composants ne sont pas encore pris en charge dans les canaux.) Ils sont par défaut les autorisations existantes de l’organisation, mais les utilisateurs peuvent modifier les autorisations avant de les envoyer pour s’assurer que tout le monde a accès.

L’ouverture de composants à partir de Teams conversation dans Office.com offre des fonctionnalités de partage en haut de la fenêtre, semblables aux options de partage offertes pour d’autres documents Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Que se passe-t-il si un fichier .fluid est endommagé ou endommagé ?

L’historique des versions vous permet d’examiner et de copier à partir des versions précédentes du fichier.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quelles applications peuvent ouvrir et modifier des fichiers .fluid ?

Les fichiers .fluid peuvent uniquement être ouverts en tant que liens dans votre navigateur, tels que Office.com, et en tant que composants Loop dans Teams conversation. S’ils sont téléchargés, ils ne peuvent pas être rouverts sans les charger d’abord vers OneDrive ou SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Les fichiers .fluid prennent-ils en charge eDiscovery ?

Les fichiers .fluid sont détectables, mais ont une prise en charge limitée du flux de travail eDiscovery. Actuellement, les fichiers .fluid sont stockés dans le OneDrive du créateur et sont disponibles pour la recherche et la collecte dans eDiscovery (Standard) et eDiscovery (Premium). Toutefois, ils ne s’affichent pas en préversion et le format d’exportation pour révision n’est pas consommable par les outils existants. Pour afficher le contenu exporté, chargez-le dans n’importe quel OneDrive. Si vous le souhaitez, vous pouvez désactiver temporairement ces expériences, comme indiqué dans la section [de gestion Paramètres](/sharepoint/manage-loop-components#settings-management).

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Si Loop est désactivé à partir du commutateur d’administration, quelle sera l’expérience utilisateur ?

Si vous désactivez ces expériences comme indiqué dans la section [de gestion Paramètres](/sharepoint/manage-loop-components#settings-management), les modifications d’expérience suivantes s’appliquent :

- Le point d’entrée de création/insertion dans Teams messagerie est masqué. Les utilisateurs ne pourront pas créer de fichiers .fluid.
- Les messages existants qui auraient été rendus sous la forme d’un composant Loop interactif s’affichent à la place sous la forme d’un lien hypertexte « composant Loop ». Aucun contenu interactif n’est affiché dans Teams.
- Lorsqu’un utilisateur final clique sur le lien hypertexte « composant Loop » ou accède à un fichier .fluid dans OneDrive Entreprise et clique pour l’ouvrir, il ouvre le fichier dans un onglet de navigateur distinct, mais les utilisateurs finaux ne peuvent pas modifier le fichier.

## <a name="known-issues"></a>Problèmes connus

- Loop composants de conversation ne peuvent pas être modifiés via application Office lors de l’utilisation de Teams sur Android.
- Si les autorisations de fichier par défaut du locataire sont définies sur *Des personnes spécifiques* (seules les personnes spécifiées par l’utilisateur) et que l’expéditeur supprime certains utilisateurs de la liste *des personnes spécifiques* dans la boîte de dialogue Autorisations lors de la création d’un composant, ces utilisateurs peuvent toujours avoir accès au contenu.
- Avec les autorisations de fichier par défaut du locataire définies sur *Personnes spécifiques* (seules les personnes spécifiées par l’utilisateur), la copie du lien vers le composant en direct et le collage dans une autre conversation nécessitent que l’expéditeur utilise la boîte de dialogue Autorisations et ajoute les destinataires dans l’option Personnes spécifiques pour accorder l’accès correctement.
- Avec les autorisations de fichier par défaut du locataire définies sur *Des personnes spécifiques* (seules les personnes spécifiées par l’utilisateur), la création d’un composant en direct dans une conversation de groupe avec plus de 20 membres nécessite que l’expéditeur sélectionne manuellement les options d’autorisation pour le composant.
- La recherche de composants Loop dans Teams recherche renvoie un lien vers le composant dans office.com, et non le message de conversation lui-même.
- Loop composants sont désactivés dans les conversations fédérées.
- Les invités B2B ne pourront pas collaborer sur un composant en direct partagé avec eux via Company Share Link. Définissez les autorisations sur **Les personnes actuellement présentes dans cette conversation** pour partager des composants avec des invités B2B.
- Loop composants ne sont pas pris en charge dans les canaux Teams.
- Loop composants de la conversation ne se chargent pas uniquement si le fichier a été déplacé vers une bibliothèque différente. Si le fichier est déplacé vers un autre dossier, il continue à se charger dans la conversation.
