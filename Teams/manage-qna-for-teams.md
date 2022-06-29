---
title: Gérer les réunions Q&A dans Teams
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Découvrez comment les administrateurs informatiques peuvent configurer, utiliser et gérer Q&A dans Teams Q&A pour une approche structurée de la collecte des questions, de l’organisation des discussions, de la suppression de messages individuels, de l’utilisation des langues disponibles et de la compréhension du cycle de vie des données, ainsi que des stratégies de rétention et de suppression des données.
ms.openlocfilehash: 17de45280809ae6c5fffdce64067fe97020965ec
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494835"
---
# <a name="manage-qa-in-teams-meetings"></a>Gérer les réunions Q&A dans Teams

Q&R est une expérience de réunion intégrée qui donne aux participants la possibilité de poser et de recevoir des réponses formelles aux questions et de s’engager dans des discussions structurées. Cette expérience est une bonne pratique pour les réunions avec plus de 10 participants.

Cet article explique comment gérer Q&A et les stratégies au niveau de l’utilisateur, qui déterminent si un organisateur peut activer teams Q&A dans leurs réunions.

> [!NOTE]
> Cette fonctionnalité est actuellement en préversion privée et n’est pas accessible publiquement. Si vous souhaitez participer au programme de préversion privée, inscrivez-vous [ici.](https://m365crmedu.powerappsportals.com/LMSSignup/)


## <a name="prerequisites"></a>Conditions préalables

- Vérifiez que vous n’avez pas bloqué [l’accès aux adresses IP et URL de Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Pour permettre aux utilisateurs de votre organisation d’ajouter Q&A aux réunions Teams, vous devez confirmer que les connexions au service yammer Office 365 sont activées dans Azure Active Directory. Suivez les étapes ci-dessous pour confirmer que les connexions sont activées :
  - Accédez au centre  > **d’administration Azure AD****Tous les services** > **Applications d’entreprise** >  Office 365 **Propriétés** **Yammer** > .
  - Pour l’option **Activé pour la connexion des utilisateurs** , sélectionnez **Oui** si nécessaire.

## <a name="who-can-use-qa"></a>Qui peut utiliser Q&A

Q&A peut être utilisé par les types d’utilisateurs suivants :

- Utilisateur standard : utilisateur disposant d’informations d’identification Microsoft 365 dans votre locataire.
- Utilisateur fédéré : utilisateur disposant d’informations d’identification Microsoft 365 pour un autre locataire.
- Utilisateur invité : tous les invités que vous ajoutez à votre Microsoft Teams, SharePoint ou Azure Active Directory.

> [!NOTE]
> Q&A ne prend pas en charge les utilisateurs anonymes pour l’instant.

Lorsque les administrateurs activent Q&A, les utilisateurs dotés du rôle organisateur peuvent activer Q&A lors de la création ou de la mise à jour des réunions. Par le biais des options de réunion Teams et Outlook, les organisateurs peuvent également supprimer Q&A des réunions où il a été ajouté précédemment pour empêcher les participants d’utiliser la fonctionnalité.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Utiliser le Centre d’administration Teams pour gérer Q&A

> [!NOTE]
> La gestion de Q&A dans le Centre d’administration n’est pas disponible en préversion publique. Utilisez PowerShell pour configurer et gérer Q&A pour vos utilisateurs.

Votre organisation peut avoir des exigences pour limiter les organisateurs qui peuvent activer Q&A. Vous pouvez utiliser le Centre d’administration Teams pour gérer les organisateurs qui peuvent activer Q&A dans les grandes réunions.
Procédez comme suit pour contrôler les organisateurs qui peuvent utiliser Q&A :

1. Dans le Centre d’administration Teams, accédez aux **stratégies de réunions** > [](/meeting-policies-participants-and-guests)
2. Sélectionnez une stratégie existante ou créez-en une et donnez-lui un nom tel que « Aucun Q&A pour ces organisateurs »
3. Faites défiler jusqu’à la section **« Participants & invités »,** sélectionnez désactiver le paramètre **« Expérience question & réponse »,** puis enregistrez la stratégie
4. Affectez la stratégie à des groupes, utilisateurs finaux ou abonnements M365 spécifiques que vous souhaitez empêcher de configurer Q&A

## <a name="use-powershell-to-manage-qa"></a>Utiliser PowerShell pour gérer Q&A

Votre organisation peut avoir des exigences pour limiter les organisateurs qui peuvent activer Q&A. Vous pouvez utiliser PowerShell pour gérer les organisateurs qui peuvent activer Q&A dans les grandes réunions.

Exemple de commande PowerShell pour activer Q&A :

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Supprimer un message individuel de Q&A dans Teams

Pour supprimer une question ou une réponse publiée dans l’application Q&A, procédez comme suit :

1. Connectez-vous au Centre de Administration Exchange en tant qu’administrateur général.
2. Accédez aux **boîtes aux lettres** **des destinataires** >  et recherchez par nom l’utilisateur qui a organisé la réunion.
3. Sélectionnez l’organisateur de la réunion, puis cliquez sur **Gérer la délégation de boîte aux lettres**. Dans la section **Lire et gérer** , sélectionnez **Modifier** > **ajouter des autorisations**.
4. Ajoutez-vous en tant que délégué de l’organisateur de la réunion, puis sélectionnez Enregistrer.
5. Ouvrez Calendrier Outlook dans Outlook Web App (et non sur le bureau), sélectionnez **Ajouter un calendrier**, puis **Ajouter à partir du répertoire**.
6. Recherchez l’organisateur de la réunion et ajoutez son calendrier à **Mes calendriers**. Les réunions de l’utilisateur sélectionné s’affichent désormais dans votre calendrier.
7. Dans votre calendrier, recherchez la réunion pour laquelle vous souhaitez supprimer du contenu, ouvrez l’enregistrement de la réunion, puis sélectionnez **Discuter avec les participants**. La sélection de la conversation avec les participants ouvre la conversation de réunion dans Teams.
8. Accédez à l’application Q&A dans la barre d’application Teams.
9. Recherchez les questions ou réponses que vous souhaitez supprimer, puis sélectionnez Supprimer.
10. Une fois que vous avez terminé de supprimer du contenu, revenez au Centre d’Administration Exchange et supprimez-vous en tant que délégué de l’organisateur de la réunion.

> [!NOTE]
> Si vous supprimez une question avant de supprimer les réponses, la première réponse à la question devient la question.
>
> Pour éviter cela, procédez comme suit dans l’ordre :
>
> 1. Identifier la question que vous souhaitez supprimer
> 2. Supprimer les réponses à la question
> 3. Supprimer la question

## <a name="available-languages-for-yammer-versus-teams"></a>Langues disponibles pour Yammer et Teams

Le Q&A est défini par défaut sur la langue de l’utilisateur pour Teams. Lorsqu’il existe une différence entre les langues disponibles pour Teams et Yammer, les valeurs par défaut de langue suivantes se produisent :

- Langue primaire la plus proche : Yammer est défini par défaut sur la langue primaire la plus proche, le cas échéant. Par exemple, Yammer ne fournit pas de version Français canadienne (fr-CA), de sorte qu’il affiche le contenu dans Français (fr-FR) à la place.
- Langue non prise en charge : si la langue n’est pas du tout fournie par Yammer, Yammer utilise par défaut l’anglais des États-Unis (en-US).

## <a name="ediscovery"></a>eDiscovery

eDiscovery pour Q&A fonctionne de la même façon que eDiscovery pour tout autre contenu Yammer.

- Si vous utilisez Teams Q&A dans l’application Teams de votre locataire, ce contenu sera disponible dans eDiscovery, quelle que soit la configuration ou l’existence de votre réseau Yammer. Pour utiliser eDiscovery pour le contenu Yammer standard, votre réseau Yammer doit être en [mode natif](/yammer/configure-your-yammer-network/overview-native-mode).
- Lorsque vous effectuez eDiscovery, vous pouvez déterminer si des messages ont été générés dans Yammer ou via Q&A dans Teams. Dans la section Métadonnées de fichier, vous pouvez trouver ces informations dans le champ Classe d’élément.
- Si votre organisation utilise le Q&A Teams, optimisé par Yammer, le contenu généré par Q&A est considéré comme du contenu Yammer et sera détectable. Pour plus d’informations sur eDiscovery dans les applications Microsoft 365, consultez [les solutions eDiscovery dans Microsoft 365.](/microsoft-365/compliance/ediscovery)

## <a name="data-storage"></a>Stockage de données

Q&Les messages A créés dans le cadre de la réunion sont stockés sous forme de messages Yammer. Ces messages sont stockés dans Yammer et ingérés pour eDiscovery.
Les fichiers sont toujours stockés dans SharePoint, qui gère toutes les stratégies et emplacements de repos de données.

Les conseils suivants expliquent comment les données de messagerie sont stockées :

- Q&Un contenu peut faire l’objet d’une recherche via eDiscovery et Advanced eDiscovery au niveau de l’utilisateur.
- Les données de message (qui incluent le contenu des messages) sont stockées dans Amérique du Nord ou l’UE par défaut (en fonction de l’emplacement réseau Yammer du client).
- Pour les locataires qui n’ont pas de réseau Yammer existant, le réseau Yammer Q&A est créé dans la région États-Unis Yammer. Les messages de votre organisation pour Q&A sont toujours stockés aux États-Unis.
- À l’instar des onglets OneNote, la suppression du Q&A d’une réunion ne supprime pas les données de la réunion. La suppression de Q&A de la réunion supprime uniquement l’accès aux données de la réunion. Si vous rajoutez l’onglet Q&A, vous verrez à nouveau toutes les conversations de réunion.

## <a name="gdpr-for-qa-in-teams"></a>RGPD pour Q&A dans Teams

Lorsque vous effectuez une demande de sujet de données par le biais du centre de Administration Microsoft 365, elle supprime automatiquement les informations de contact des utilisateurs de tout leur contenu dans le Q&A.

## <a name="data-lifecycle-for-qa-in-teams"></a>Cycle de vie des données pour Q&A dans Teams

Le cycle de vie des données générées par Q&A dans Teams dépend de vos paramètres de rétention des données Yammer dans le Centre de conformité. Si vous supprimez définitivement tous les utilisateurs de la réunion qui ont reçu une copie des messages Q&A dans leur partition de substrat via Azure Active Directory, Yammer supprimera sa copie du contenu Q&A pour cette réunion dans les 30 jours suivant la suppression de l’utilisateur.

## <a name="retention-and-deletion"></a>Rétention et suppression

La rétention du contenu suit les stratégies de rétention définies pour Yammer, que vous ayez ou non des stratégies différentes pour Yammer et Teams.

> [!NOTE]
> Si votre réseau Yammer n’est pas en mode natif, les stratégies créées ici s’appliquent uniquement aux données Q&A teams. En mode natif, tous les utilisateurs Yammer se trouvent dans Azure Active Directory (Azure AD), tous les groupes sont des groupes Microsoft 365 et tous les fichiers sont stockés dans SharePoint Online.

## <a name="faq"></a>FAQ

**Q : Comment faire exporter du contenu Q&A ?**

**Un:** Q&Un contenu est stocké dans le Centre de conformité Microsoft 365 et accessible via eDiscovery. Les itérations ultérieures incluront un rapport de mise en évidence de réunion et des fonctionnalités d’exportation pour les organisateurs de réunion.

**Q : Q&A prend-il en charge les fonctionnalités multigéographiques microsoft 365 ?**

**Un:** Q&A ne prend actuellement pas en charge les fonctionnalités multigéographiques de Microsoft 365. Q&Les données A sont stockées dans Amérique du Nord ou l’UE par défaut (en fonction de l’emplacement réseau Yammer du client).

**Q : Où puis-je en savoir plus sur les réunions structurées ?**

**Un:** Suivez ces [bonnes pratiques](/MicrosoftTeams/quick-start-meetings-live-events) pour héberger des réunions volumineuses réussies dans Microsoft Teams.

**Q : Quelle est la différence entre la configuration de Q&A via l’App Store Teams et l’utilisation des options de réunion ?**

**Un:** Bien qu’il n’y ait aucune différence entre l’expérience utilisateur du participant et du modérateur, Q&A doit être configuré uniquement à l’aide des options de réunion. L’application Q&A dans l’App Store Teams sera déconseillée d’ici la fin de 2022. Il est donc préférable d’utiliser les options de réunion pour configurer Q&A dans vos réunions.
