---
title: Gérer les questions&R dans les réunions Teams
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Découvrez comment les administrateurs informatiques peuvent configurer, utiliser et gérer les Q&R dans Teams Q&R pour une approche structurée de la collecte de questions, de l’organisation des discussions, de la suppression de messages individuels, de l’utilisation des langues disponibles et de la compréhension du cycle de vie des données, ainsi que des stratégies de conservation et de suppression des données.
ms.openlocfilehash: 3d85dbe4c9035a9de0ccb47557735bb797bdf244
ms.sourcegitcommit: 94e3f5e8dcfe8b3098ed8de2e4397e2338038f03
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/29/2022
ms.locfileid: "69177720"
---
# <a name="manage-qa-in-teams-meetings"></a>Gérer les questions&R dans les réunions Teams

Q&A permet aux présentateurs de répondre aux questions des participants et d’y répondre en temps réel. Cette fonctionnalité est idéale pour les grandes réunions structurées, comme les assemblées publiques, les webinaires, toutes les mains et les formations.

Cet article explique comment gérer les stratégies Q&A et utilisateur, qui déterminent si un organisateur peut activer teams Q&R dans ses réunions.

## <a name="prerequisites"></a>Conditions préalables

- Vérifiez que vous n’avez pas bloqué [l’accès aux adresses IP et URL de Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Pour permettre aux utilisateurs de votre organisation d’ajouter des Q&R aux réunions Teams, vous devez vérifier que les connexions au service Yammer Office 365 sont activées dans Azure Active Directory. Suivez les étapes ci-dessous pour vérifier que les connexions sont activées :
  - Accédez au Centre  > **d’administration Azure AD****Tous les services** >  Applications  > **d’entreprise** **Office 365 Propriétés Yammer** > .
  - Pour l’option **Activé pour la connexion des utilisateurs ?** , sélectionnez **Oui** si nécessaire.
- Vérifiez que vous n’avez pas bloqué l’application Q&A (native) dans les [applications Teams](/MicrosoftTeams/manage-apps)

## <a name="who-can-use-qa"></a>Qui peut utiliser Q&R

Q&A peut être utilisé par les types d’utilisateurs suivants :

- Utilisateur standard : utilisateur avec Microsoft 365 informations d’identification dans votre locataire.
- Utilisateur fédéré : utilisateur avec Microsoft 365 informations d’identification à un autre locataire.
- Utilisateur invité : tous les invités que vous ajoutez à votre Microsoft Teams, SharePoint ou Azure Active Directory.

> [!NOTE]
> Q&R n’est pas disponible dans GCC.

Lorsque les administrateurs activent Q&R, les utilisateurs disposant du [rôle organisateur](https://aka.ms/GetQnA) peuvent activer Q&R lors de la création ou de la mise à jour des réunions. Par le biais des options de réunion Teams et Outlook, les organisateurs peuvent également supprimer Q&R des réunions où elle a été précédemment ajoutée pour empêcher les participants d’utiliser la fonctionnalité.
> [!NOTE]
> Q&R ne sera pas disponible pour afficher uniquement les participants qui rejoignent la réunion au-delà de la capacité de réunion.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Utiliser le Centre d’administration Teams pour gérer les questions&R

Votre organisation peut avoir des exigences pour limiter les organisateurs qui peuvent activer Q&R. Vous pouvez utiliser le Centre d’administration Teams pour gérer les organisateurs qui peuvent activer Q&R dans les grandes réunions.
Procédez comme suit pour contrôler les organisateurs qui peuvent utiliser Q&R :

1. Dans le Centre d’administration Teams, accédez à **Stratégies de**[**réunion**](/meeting-policies-participants-and-guests) réunions  > 
2. Sélectionnez une stratégie existante ou créez-en une et attribuez-lui un nom tel que « Aucun Q&A pour ces organisateurs »
3. Faites défiler jusqu’à la section **« Participants & Invités »,** sélectionnez désactiver pour le paramètre **« Expérience de question & réponse »,** puis enregistrez la stratégie.
4. Attribuez la stratégie à des groupes, des utilisateurs finaux ou des abonnements M365 spécifiques que vous souhaitez empêcher de configurer Q&R

## <a name="use-powershell-to-manage-qa"></a>Utiliser PowerShell pour gérer les questions&R

Votre organisation peut avoir des exigences pour limiter les organisateurs qui peuvent activer Q&R. Vous pouvez utiliser PowerShell pour gérer les organisateurs qui peuvent activer Q&R dans les grandes réunions.

Exemple de commande PowerShell pour activer Q&R :

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Supprimer un message individuel de Q&R dans Teams

Pour supprimer une question ou une réponse publiée dans l’application Q&R, procédez comme suit :

1. Connectez-vous au Centre Administration Exchange en tant qu’administrateur général.
2. Accédez à **Boîtes aux lettres** **destinataires** >  et recherchez par nom l’utilisateur qui a organisé la réunion.
3. Sélectionnez l’organisateur de la réunion, puis cliquez sur **Gérer la délégation de boîte aux lettres**. Dans la section **Lecture et gestion** , sélectionnez **Modifier** > **Ajouter des autorisations**.
4. Ajoutez-vous en tant que délégué de l’organisateur de la réunion et sélectionnez Enregistrer.
5. Ouvrez Calendrier Outlook dans Outlook Web App (et non sur le bureau), sélectionnez **Ajouter un calendrier**, puis **Ajouter à partir du répertoire**.
6. Recherchez l’organisateur de la réunion et ajoutez son calendrier à **Mes calendriers**. Les réunions de l’utilisateur sélectionné s’affichent désormais dans votre calendrier.
7. Dans votre calendrier, recherchez la réunion pour laquelle vous souhaitez supprimer du contenu, ouvrez l’enregistrement de réunion, puis sélectionnez **Discuter avec les participants**. La sélection d’une conversation avec les participants ouvre la conversation de réunion dans Teams.
8. Accédez à l’application Q&A dans la barre de l’application Teams.
9. Recherchez les questions ou réponses que vous souhaitez supprimer, puis sélectionnez Supprimer.
10. Une fois que vous avez terminé de supprimer du contenu, revenez au Centre Administration Exchange et supprimez-vous en tant que délégué de l’organisateur de la réunion.

> [!NOTE]
> Si vous supprimez une question avant de supprimer les réponses, la première réponse à la question devient la question.
>
> Pour éviter cela, procédez comme suit :
>
> 1. Identifier la question que vous souhaitez supprimer
> 2. Supprimer les réponses à la question
> 3. Supprimer la question

## <a name="available-languages-for-yammer-versus-teams"></a>Langues disponibles pour Yammer et Teams

Le Q&R est défini par défaut sur la langue de l’utilisateur pour Teams. Lorsqu’il existe une différence entre les langues disponibles pour Teams et Yammer, les langues par défaut suivantes se produisent :

- Langue principale la plus proche : Yammer utilise par défaut la langue principale la plus proche, si disponible. Par exemple, Yammer ne fournit pas de version Français canadienne (fr-CA), de sorte qu’il affiche le contenu dans Français (fr-FR) à la place.
- Langue non prise en charge : si la langue n’est pas fournie par Yammer, Yammer est défini par défaut sur l’anglais américain (en-US).

## <a name="ediscovery"></a>eDiscovery

eDiscovery pour Q&R fonctionne de la même façon que eDiscovery pour tout autre contenu Yammer.

- Si vous utilisez Teams Q&A dans l’application Teams de votre locataire, ce contenu sera disponible dans eDiscovery, quelle que soit la configuration ou l’existence de votre réseau Yammer. Pour utiliser eDiscovery pour du contenu Yammer standard, votre réseau Yammer doit être en [mode natif](/yammer/configure-your-yammer-network/overview-native-mode).
- Lorsque vous effectuez eDiscovery, vous pouvez déterminer si les messages ont été générés dans Yammer ou via Q&R dans Teams. Dans la section Métadonnées du fichier, vous trouverez ces informations dans le champ Classe d’élément.
- Si votre organisation utilise teams Q&A, alimenté par Yammer, le contenu généré par Q&A est considéré comme du contenu Yammer et sera détectable. Pour plus d’informations sur eDiscovery dans les applications Microsoft 365, consultez [Solutions eDiscovery dans Microsoft 365.](/microsoft-365/compliance/ediscovery)
- Si l’organisateur de la réunion active la publication anonyme, les questions publiées par les participants sont ingérées dans la boîte aux lettres de l’organisateur pour eDiscovery.

## <a name="data-storage"></a>Stockage de données

Q&Les messages créés dans le cadre de la réunion sont stockés en tant que messages Yammer. Ces messages sont stockés dans Yammer et ingérés pour eDiscovery.
Les fichiers sont toujours stockés dans SharePoint, qui gère toutes les stratégies et emplacements de repos des données.

Les conseils suivants expliquent comment les données de messagerie sont stockées :

- Le contenu Q&A peut faire l’objet d’une recherche via eDiscovery et Advanced eDiscovery au niveau de l’utilisateur.
- Les données de message (qui incluent le contenu des messages) sont stockées dans Amérique du Nord ou dans l’UE par défaut (en fonction de l’emplacement réseau Yammer du client).
- Pour les locataires qui n’ont pas de réseau Yammer existant, le réseau Yammer Q&A est créé dans la région États-Unis Yammer. Les messages de votre organisation pour Q&R seront toujours stockés aux États-Unis.
- Comme pour les onglets OneNote, la suppression du Q&A d’une réunion ne supprime pas les données de la réunion. La suppression de Q&A de la réunion supprime uniquement l’accès aux données de la réunion. Si vous rajoutez l’onglet Q&R, vous verrez à nouveau toutes les conversations de réunion.

## <a name="gdpr-for-qa-in-teams"></a>RGPD pour Q&R dans Teams

Lorsque vous effectuez une demande de personne concernée par le biais du Centre Administration Microsoft 365, elle supprime automatiquement les informations de contact des utilisateurs de tout leur contenu dans le Q&R.

## <a name="data-lifecycle-for-qa-in-teams"></a>Cycle de vie des données pour Q&R dans Teams

Le cycle de vie des données générées par Q&A dans Teams dépend de vos paramètres de conservation des données Yammer dans le Centre de conformité. Si vous supprimez définitivement tous les utilisateurs de la réunion qui ont reçu une copie des messages Q&A dans leur partition de substrat via Azure Active Directory, Yammer supprimera sa copie du contenu Q&A pour cette réunion dans les 30 jours suivant la suppression de l’utilisateur.

## <a name="retention-and-deletion"></a>Rétention et suppression

La rétention du contenu suit les stratégies de rétention définies pour Yammer, que vous ayez ou non des stratégies différentes définies pour Yammer et Teams.

> [!NOTE]
> Si votre réseau Yammer n’est pas en mode natif, les stratégies créées ici s’appliquent uniquement aux données Q&R Teams. En mode natif, tous les utilisateurs yammer se trouvent dans Azure Active Directory (Azure AD), tous les groupes sont Microsoft 365 groupes et tous les fichiers sont stockés dans SharePoint Online.

## <a name="faq"></a>FAQ

**Q : Comment faire exporter du contenu Q&R ?**

**Un:** Le contenu Q&A est stocké dans le Centre de conformité Microsoft 365 et accessible via eDiscovery. Les futures itérations incluront un rapport de mise en évidence de la réunion et une fonctionnalité d’exportation pour les organisateurs de réunion.

**Q : Q&A prend-il en charge les fonctionnalités multigéographiques Microsoft 365 ?**

**Un:** Q&A ne prend actuellement pas en charge les fonctionnalités multigéographiques Microsoft 365. Les données Q&A sont stockées dans Amérique du Nord ou l’UE par défaut (en fonction de l’emplacement réseau Yammer du client).

**Q : Où puis-je en savoir plus sur les réunions structurées ?**

**Un:** Suivez ces [bonnes pratiques](/MicrosoftTeams/quick-start-meetings-live-events) pour organiser des réunions volumineuses réussies dans Microsoft Teams.

**Q : Quelle est la différence entre la configuration de Q&A via l’App Store Teams et l’utilisation des options de réunion ?**

**Un:** Nous avons simplifié l’activation des Q&R via les options de réunion. À compter d’août 2022, l’application Q&A dans l’App Store Teams n’est plus prise en charge. Par conséquent, les Q&R ne doivent être activés que par le biais des options de réunion. Si vous êtes l’organisateur de réunions où Q&A a été activé via le magasin d’applications Teams, supprimez l’application Q&A et activez uniquement les options de réunion.

**Q : Pourquoi deux icônes Q&R s’affichent-ils dans ma réunion ?**

**Un:** Vous voyez deux icônes Q&R dans votre réunion, car Q&R a également été activé via options de réunion. Supprimez l’application Q&A qui a été ajoutée via le App Store Teams en suivant les instructions ci-dessous. Effectuez cette opération pour toutes vos réunions où vous avez précédemment ajouté Q&R via le magasin d’applications Teams.

**Comment supprimer l’application Q&A ajoutée à partir de l’App Store Teams.**

1. Sur le bureau Teams, participez à la réunion où vous avez précédemment ajouté Q&R.

2. Dans le volet supérieur, sélectionnez la deuxième occurrence de l’icône Q&R dans la fenêtre Réunion Teams : il s’agit de l’expérience Q&A qui a été ajoutée via le App Store Teams.

3. Avec l’onglet Q&A sélectionné ouvert, cliquez sur les points de suspension, puis cliquez sur « Supprimer ». Cela supprimera l’expérience Q&A qui a été ajoutée via le magasin d’applications Teams.

4. Cliquez sur « Supprimer » pour supprimer définitivement l’expérience Q&A qui a été ajoutée via l’App Store Teams.

> [!NOTE]
> Seule l’application Q&A ajoutée via le magasin d’applications Teams aura des points de suspension pour supprimer l’application Q&R. L’expérience Q&A activée via les options de réunion n’aura pas de points de suspension et ne peut pas être supprimée d’ici.

Voilà! Maintenant, il n’existe qu’une seule expérience Q&R, optimisée par les options de réunion. L’application Q&A ajoutée via le magasin d’applications Teams est supprimée.
