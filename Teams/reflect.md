---
title: Guide d’administration informatique de Reflect dans Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Un guide d’administration informatique de Reflect dans Microsoft Teams pour l’éducation.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62aa82c42acf3ca4477da6da60b1faec6c847be1
ms.sourcegitcommit: 0d61ca384e7d76612743de41c8fea4729072fb5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "64837447"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a>Guide d’administration informatique de Reflect dans Microsoft Teams

Ce document fournit des informations sur [Reflect](https://aka.ms/reflect) , qui fait partie intégrante de [Insights dans Microsoft Teams](class-insights.md). Reflect aide les étudiants à reconnaître et à parcourir dans leurs émotions en leur offrant des opportunités régulières de partager et d’être entendus. Reflect peut aider les apprenants à étendre sur leur vocabulaire émotionnel et à approfondir leur empathie pour leurs paires tout en fournissant des commentaires utiles aux enseignants pour une communauté de classe saine.

Cette application de contrôle utilise des emojis et une granularité émotionnelle inspirée de la recherche pour aider les enseignants à ajouter une formation sociale et émotionnelle à leur routine déjà chargée.


## <a name="privacy-and-security"></a>Confidentialité et sécurité
Réflexions suit les mêmes normes de confidentialité et de sécurité que [Éducation Insights](class-insights.md) pour protéger les informations sensibles des étudiants.

Réflexions, dans le cadre de Microsoft 365, respecte les réglementations nationales, régionales et sectorielles en matière de collecte et d’utilisation des données, notamment [RGPD](/compliance/regulatory/gdpr) et le [FERPA (Family Educational Rights and Privacy Act)](/compliance/regulatory/offering-ferpa) qui protège la confidentialité des dossiers d’enseignement des étudiants.

Les données appartiennent à l’établissement, et Microsoft se contente de collecter et de stocker les données. Le personnel de Microsoft ne peut ni accéder aux données ni les consulter, sauf lors d’opérations d'audit (impliquant parfois des récupérations de données) requises pour assurer le bon fonctionnement du service, et ce dans le respect des règles de conformité.

Les étudiants ne voient *jamais* les noms des autres étudiants, seulement leurs réponses. Bien qu’;ils puissent voient la distribution des réponses, ils ne peuvent *pas* voir les noms associés à chaque réflexion. 

> [!NOTE]
> Si moins de cinq étudiants répondent, aucune donnée n’est affichée aux étudiants. Cela permet de minimiser la possibilité pour les étudiants d’identifier les réponses des autres étudiants.

> [!TIP]
> * Si vous souhaitez en savoir plus sur la protection de vos données par Microsoft, veuillez visiter le [Centre de gestion de la confidentialité de Microsoft](https://www.microsoft.com/trust-center).
> * Visitez [Offres de conformité Microsoft](/compliance/regulatory/offering-home) pour découvrir comment Microsoft 365 aider votre établissement à respecter les normes de conformité réglementaire.

## <a name="data-collection-and-storage"></a>Collecte et stockage de données
Les données appartiennent à l’établissement scolaire, et Microsoft se contente de collecter et de stocker les données. Le personnel de Microsoft ne peut ni accéder aux données ni les consulter, sauf lors d’opérations d'audit (impliquant parfois des récupérations de données) requises pour assurer le bon fonctionnement du service, et ce dans le respect des règles de conformité.

Les données sont stockées dans Insights. Par défaut, Insights est activé. Lorsque vous désactivez Insights, nous **supprimons toutes les données collectées** pour Reflect. Si vous réactivez Insights, nous commencerons à collecter des données à partir de l’heure de la réactivation.

Dans le [Guide d’administration informatique Insights](class-insights.md), vous pouvez découvrir le fonctionnement de Insights (y compris les emplacements de stockage) et [comment désactiver ou activer Insights](class-insights.md#turn-insights-on-or-off) lorsque vous voulez supprimer les données ou activer le service.

Les données des étudiants sont collectées dans Reflect, bien que les données invités ne le sont pas. **Si un étudiant est défini comme un invité, ses données ne sont pas collectées.** 

## <a name="enable-reflect"></a>Activer Reflect
Si vous gérez la stratégie de configuration de l’application pour votre établissement, assurez-vous que Reflect est *autorisé* dans votre client. Vous pouvez également ajouter Reflect aux équipes de classe concernées à partir du centre d’administration Teams.

Pour permettre à un utilisateur d’installer et d’interagir avec une application, vous devez autoriser l’application au niveau de l’organisation sur la page **Gérer les applications** et la **stratégie d’autorisation d’application** affectée à l’utilisateur.

Si vous avez précédemment défini que chaque application doit être autorisée, veuillez accéder à la page Gérer des applications et « autoriser » Reflect. **Lorsque vous bloquez une application, l’application ne s’affiche pas dans Teams pour les utilisateurs de votre organisation.**

> [!NOTE]
> Pour accéder à l’application Reflect, vous devez avoir une licence A1, A3 ou A5 pour Microsoft 365.

> [!TIP]
> Pour plus d’informations, lisez [comment autoriser une application ou l’ajouter à une équipe de classe](manage-apps.md#allow-and-block-apps).

## <a name="where-do-educators-find-reflect"></a>Où les enseignants peuvent-ils trouver Reflect ?
Une fois que vous avez activé Reflect, les enseignants peuvent se rendre en classe et sélectionner l’option **Nouvelle conversation**. Ils sélectionnent ensuite «**...**» pour ouvrir les extensions de messagerie et entrer **Reflect** dans la barre de recherche. La boîte de dialogue les guide dans la définition de la question et des personnes peuvent voir.

:::image type="content" source="media/reflect-add-app.png" alt-text="Ajouter Reflect à une équipe de classe.":::

Ils peuvent cliquer avec le bouton droit sur l’icône Reflect, puis sélectionner **Épingler** pour y accéder facilement.

:::image type="content" source="media/reflect-pin-app.png" alt-text="Épingler l’application Reflect.":::

> [!TIP]
> Vous pouvez également localiser l’application Reflect via ce lien : [https://aka.ms/getReflect](https://aka.ms/getReflect)

> [!TIP]
> Pour plus d’informations, consultez [Page de support de Réflexions](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a). Cette page fournit des instructions pour les enseignants et les étudiants et explique comment créer leur premier contrôle de Réflexions.
