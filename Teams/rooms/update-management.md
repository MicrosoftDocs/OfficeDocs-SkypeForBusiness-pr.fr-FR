---
title: gestion des mises à jour Salles Microsoft Teams
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: surveillance proactive de vos salles de réunion.
f1keywords: ''
ms.openlocfilehash: 2311d17c5d60b7c9eb845570ce24c5f6db507717
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057064"
---
# <a name="update-management"></a>Gestion des mises à jour 
Une salle de réunion moderne est équipée d’un appareil Salles Microsoft Teams et d’autres périphériques tels qu’une caméra, un microphone ou un haut-parleur, et potentiellement plus d’appareils pour créer une expérience de réunion inclusive et efficace. L’équipement de différents types d’OEM fournit l’expérience organisationnelle exacte souhaitée; toutefois, ils doivent être maintenus avec des logiciels et des microprogrammes sur une base continue.  

Les services gérés pour Salles Microsoft Teams fournissent l’assurance que chaque salle de votre organisation sera maintenue aux niveaux recommandés pour fournir une salle qui est toujours prête et fonctionne correctement. L’objectif de Microsoft est de réduire la complexité et le travail d’étape de votre personnel opérationnel grâce à l’intelligence et à l’automatisation. La résolution des problèmes ou les diagnostics sont effectués le plus rapidement possible. 

## <a name="transitioning-a-device-to-managed-services"></a>Transition d’un appareil vers des services gérés 
L’intégration des appareils de salle aux services managés a généralement un historique et une pratique de gestion des modifications différents de nos conseils.  

- Pour tirer parti des services managés, vous devez effectuer la transition de la gestion des modifications pour toutes les mises à jour du portefeuille des services gérés.
- Plusieurs sources de contrats SLA d’impact sur la gestion des modifications, car il existe une découverte et une correction qui redémarrent si un incident se produit dans la salle.
- Microsoft a implémenté des contrôles et des vérifications pour implémenter des stratégies qui peuvent différer d’une organisation à l’autre, et la possibilité d’intervenir dans des situations exceptionnelles.
- Finalement, les appareils de salle seront mis à jour selon des normes communes, à l’exception des exceptions en raison de problèmes liés à une installation matérielle spécifique.  

## <a name="transitioning-devices-basic-readiness-checks"></a>Transition d’appareils : contrôles de préparation de base 
La plupart des échecs inattendus résultent des modifications apportées à l’image de base avec un historique incertain de la gestion des modifications. 

Les contrôles de préparation simples suivants sont recommandés :  

- **Image de base** : l’image de base doit être de l’OEM spécifique. Si l’appareil a été reconstruit dans le passé et affiche des défaillances ou des comportements inattendus sur des tâches courantes, l’image de base doit être restaurée. Nous pouvons fournir de l’aide, mais nous ne pouvons pas régénérer à distance l’appareil de la salle. Vous aurez donc besoin d’un technicien de site local.  
- **Système d’exploitation de base, édition :** Le système d’exploitation et l’édition de base doivent correspondre aux exigences des appareils Salles Microsoft Teams. Si ce n’est pas le cas, il doit être corrigé dans le cadre de l’intégration. Salles Microsoft Teams nécessite les références SKU Windows 10 IoT Entreprise ou Windows 10 Entreprise sous Semi-Annual options de maintenance du canal. Pour plus d’informations, consultez les [conseils officiels du MTR](rooms-lifecycle-support.md#windows-10-release-support) .

## <a name="readiness-checks"></a>Vérifications de préparation

Il existe quelques prérequis pour la réception des mises à jour des services managés : 

|Logiciels |Aide |
|:- |:- |
|Logitech Sync Services  |Doit être installé et exécuté sur les appareils de salle de réunion Logitech. Les services de synchronisation requis sont installés automatiquement à partir de Windows Mises à jour, sauf si elles sont bloquées. Le package de synchronisation complète peut également être installé. |
|mises à jour du système d’exploitation Windows |Doit être maintenu activé et non redirigé vers WSUS, ni bloqué du point de vue de la mise en réseau. Ni les stratégies GPO ni GDM ne doivent être utilisées pour gérer les mises à jour du système d’exploitation. |
|mises à jour Microsoft Store   |Doit être désactivé. Managed Services désactive les mises à jour du Windows Store si elle est activée. |
|Logiciel antivirus |Si vous exécutez des logiciels AV sur ces appareils, vous devez vous assurer qu’AV a des exclusions en place pour Teams et Skype dlls. Pour plus d’informations, voir ici. |
|Logiciels supplémentaires |Des logiciels supplémentaires tels que l’affichage de bureau à distance tiers, etc. doivent être examinés avec Managed Services pour éliminer les effets secondaires. |
|Gestion des modifications supplémentaires|Peut interférer avec les mises à jour couvertes et ne doit pas être introduite. |

## <a name="managed-updates--how-it-works"></a>Mises à jour gérées : fonctionnement 
Il existe deux façons principales de gérer les mises à jour :  

- **Géré automatiquement** : les mises à jour sont installées dans votre appareil de salle en fonction de l’évaluation des services managés. Aucune intervention n’est requise pour les mises à jour gérées dans notre portefeuille.
- **Anneau validé** : configurez un système d’anneau pour afficher un aperçu des mises à jour sur des appareils spécifiques afin de pouvoir les surveiller sans le travail de jambe associé. La configuration en anneau fournit une couche supplémentaire de diligence raisonnable avant les déploiements à grande échelle.  

### <a name="automatically-managed"></a>Géré automatiquement

Si vous choisissez d’être géré automatiquement, aucune action n’est nécessaire pour les mises à jour de votre part. Toutefois, vous devez passer en revue le portefeuille actuel de mises à jour prises en charge par Managed Services. Le portefeuille reçoit constamment de nouveaux ajouts, et il est de notre priorité de couvrir les mises à jour les plus fréquentes et les plus percutantes pour garantir la stabilité de votre chambre. Consultez la liste actuelle (sous la section « Update Management » de ce document) pour planifier toute gestion des modifications supplémentaire nécessaire à votre organisation.  

**Recommandation:** N’installez pas les mises à jour couvertes par Managed Services sur un appareil géré par vous-même. Si vous rencontrez des problèmes, signalez un incident dans le portail.

### <a name="ring-validation"></a>Validation en anneau

Lorsque vous choisissez la validation en anneau, passez en revue les sections suivantes sur le fonctionnement des anneaux dans Les services managés et les options disponibles pour la personnaliser pour votre organisation. Même avec la validation en anneau, Managed Services tente de s’assurer que les salles ne sont pas dépassées sur les mises à jour recommandées. Selon la situation, une salle peut recevoir des mises à jour de « rattrapage » pour s’assurer qu’elle est conforme aux recommandations du service managé.  

 Recherchez les annonces sur la page d’accueil du portail et dans la documentation des services managés à mesure que de nouveaux types de logiciels et de microprogrammes deviennent disponibles dans le portefeuille. Étant donné que les experts des services managés examinent quotidiennement les versions des mises à jour sur notre portefeuille d’appareils, ils traitent des problèmes spécifiques et ciblent les mises à jour en fonction des besoins.  

### <a name="scheduling"></a>Planification 
Les mises à jour managées sont planifiées pour les salles en fonction de l’équipement de la salle et si elles ne répondent pas aux normes des services managés pour les logiciels et microprogrammes applicables. 

- Pour aider nos clients à répondre aux exigences de gestion des modifications, le déploiement des mises à jour démarre **le mercredi** dans l’anneau intermédiaire. Si une mise à jour critique est requise, nous allons contourner cette planification et la publier dès qu’elle est disponible. 

- Les mises à jour sont séquencées en fonction des besoins dans une salle particulière. 
- Si vous avez des anneaux d’installation pour valider les mises à jour, la mise à jour progresse dans l’ordre de l’anneau. 
- Une nouvelle mise à jour peut remplacer une mise à jour mise en file d’attente si nous déterminons que la stabilité de la salle est améliorée en fonction de votre situation.  
- Les mises à jour sont généralement appliquées au cours de notre fenêtre de maintenance nocturne, c’est-à-dire à l’heure locale de **la salle de 12h00 à 5h00** pour éviter tout type d’interruptions. 

## <a name="microsoft-teams-rooms-app-update-lifecycle-policy"></a>Salles Microsoft Teams stratégie de cycle de vie des mises à jour d’application 
La stratégie de support de l’équipe d’ingénierie MTR indique que tous les supports se terminent après l’expiration du cycle de vie de douze (12) mois pour une version ou si plus de deux mises à jour ont été publiées depuis. Ensuite, les clients doivent mettre à jour vers une version prise en charge. Reportez-vous [à Salles Microsoft Teams prise en charge de la version de l’application - Microsoft Teams | Microsoft Docs](rooms-lifecycle-support.md) pour obtenir une description détaillée du service.

Pour maintenir une norme uniforme dans toutes nos salles gérées et pour nous permettre d’identifier efficacement les problèmes de tendance, nous allons prendre en charge et déployer les deux dernières versions majeures ou mineures (N, N-1) du logiciel de l’application MTR conformément aux conditions générales des services de support et d’abonnement. Nous mettons automatiquement à jour les salles non conformes, en contournant les anneaux de mise à jour si nécessaire. 

La stratégie N-1 s’applique également aux logiciels tiers.  

## <a name="update-management-experience-walk-through"></a>Expérience de gestion des mises à jour pas à pas  
Pour afficher les mises à jour, connectez-vous au portail des services managés et accédez à la page Mises à jour.

![Capture d’écran des mises à jour des services managés](../media/update-management-001.jpg)

Le volet Mises à jour affiche une vue d’ensemble générale de la gestion des mises à jour pour vos salles avec les onglets suivants :

- **Mises à jour** : mises à jour logicielles ou de microprogrammes que Managed Services orchestre au sein de votre organisation.  
- **Salles** : l’onglet Salles offre une vue sur les salles et les anneaux auxquels chaque chambre appartient.
- **Anneaux** : l’onglet Anneaux affiche les anneaux de salles de votre organisation.

### <a name="updates"></a>Updates  

Cette vue affiche les mises à jour pertinentes pour votre locataire et leur état respectif. Pour afficher les mises à jour passées qui ne sont plus actives, **sélectionnez le bouton Bascule Inclure les mises à jour passées** sur ON.  

Toute mise à jour peut se trouver dans l’un des états suivants :

| Statut | Description |
|:- |:- |
| Prévue | Une mise à jour est planifiée pour les salles d’un anneau donné. Gardez à l’esprit qu’une mise à jour s’affiche uniquement après que la progression a atteint l’anneau dans lequel se trouve la salle. Par exemple, si une nouvelle mise à jour se trouve dans l’anneau de mise en lots, elle n’affiche que les salles planifiées dans l’anneau de mise en lots.<br></br><p> Les autres anneaux auront l’état « Non requis » tant que la mise à jour n’aura pas atteint cet anneau.</p> |
| En cours | Une mise à jour est en cours et les anneaux individuels affichent l’état. Cet état indique l’état global de l’anneau. Par conséquent, si une mise à jour s’applique à une seule salle de l’anneau intermédiaire dans votre locataire, la mise à jour a l’état « En cours » jusqu’à ce que l’anneau exécutif soit atteint. |
| Terminé avec des échecs | Une mise à jour a terminé la progression de tous vos anneaux configurés et a échoué dans au moins une salle. |
| Terminé | Une mise à jour a terminé la progression de tous vos anneaux configurés et installée avec succès sur toutes les salles applicables.|
| Déconseillée | Une mise à jour a été désactivée. Le déploiement supplémentaire est interrompu. Cela est courant, car la mise à jour a été remplacée par une nouvelle version. |
| Pause | Une mise à jour est dans un état suspendu. |
| Non obligatoire | La mise à jour n’est pas encore évaluée pour la salle ou ne s’applique pas à la salle. |

### <a name="rooms"></a>Chambres  

L’onglet Salles affiche toutes les salles de votre locataire et l’anneau auquel elles appartiennent.  

![Capture d’écran de tous les anneaux de locataire et de leurs chambres](../media/update-management-002.jpg)

Pour configurer l’anneau auquel une salle doit appartenir :  

1. Cliquez sur la salle pour afficher la vue détaillée.  
1. Sous **Anneau**, cliquez sur **Modifier**.  
1. Sélectionnez l’anneau auquel la salle doit appartenir.  
1. Cliquez sur **Affecter**.  

La vue d’espace détaillée affiche les mises à jour pertinentes et leur état sous le nœud **Mises à jour** .  

![Capture d’écran des mises à jour et des modifications pertinentes](../media/update-management-003.jpg)

### <a name="rings"></a>Anneaux  

Les anneaux sont utilisés pour réduire le risque de problèmes dérivés du déploiement des mises à jour des fonctionnalités. Pour ce faire, déployez progressivement la mise à jour sur l’ensemble du site. Chaque anneau doit avoir une liste de Microsoft Teams salles et un calendrier de déploiement correspondant. La définition d’anneaux est généralement un événement unique (ou au moins peu fréquent), mais le service informatique doit revoir ces groupes de temps à autre pour s’assurer que le séquencement est toujours correct.  

L’onglet **Anneaux** répertorie tous les anneaux dans votre locataire. Il existe trois anneaux préconfigurés :  

- **Préproduction** : attribuez des salles à l’anneau de mise en lots, qui est votre banc d’essai. Toutes les nouvelles mises à jour seront déployées ici en premier. En règle générale, vous devez vous assurer que votre anneau de préproduction représente les salles présentant la diversité des types d’appareils dans votre environnement. S’il existe certains types de salles avec une configuration inhabituelle ou un historique de problèmes de vue, envisagez de les représenter dans Staging.

- **Général** : Par défaut, toutes les chambres sont placées dans cet anneau. La plupart des appareils de salle utilisés dans l’entreprise appartiennent à cette catégorie. 

- **Cadre :** Ce groupe doit inclure vos salles les plus importantes dans lesquelles vous souhaitez réduire les perturbations de manière proactive. Un bon exemple est une grande salle de conférence utilisée pour les réunions de direction ou les grandes réunions d’équipe. 

### <a name="specifying-rollout-timeline"></a>Spécification de la chronologie du déploiement

Les mises à jour ne peuvent pas dépasser 60 jours pour se terminer sur tous les anneaux.  

|Paramètre |Explication |
|:- |:- |
|Période de report|Une fois qu’une mise à jour commence par le premier anneau, la période de report correspond au délai de quelques jours avant le lancement de la mise à jour sur cet anneau.|
|Durée du déploiement|<p>Une fois la mise à jour démarrée sur cet anneau, c’est le moment de déployer dans cet anneau. Par exemple, si la durée est de 5 jours, elle est déployée sur 5 jours dans les salles de cet anneau une fois la mise à jour démarrée sur cet anneau.|
|Période de test|Nombre de jours pendant lesquels tester/valider la mise à jour dans un anneau une fois appliquée à l’anneau. La période de test commence une fois le déploiement terminé et, une fois l’opération terminée, la mise à jour passe à l’anneau suivant.|
|Heure d’achèvement|La colonne « Temps d’achèvement » indique le nombre total de jours (durée du déploiement + période de test) pour que cet anneau se termine.|
|Durée totale|En bas se trouve la ligne « Total » qui indique la durée d’exécution d’une mise à jour entre le premier et le dernier anneau.|

### <a name="creating-custom-rings"></a>Création d’anneaux personnalisés

1. Accédez à l’onglet **Anneaux** .  
1. Cliquez sur **Ajouter un anneau**.  
1. Spécifiez l’ordre dans lequel cet anneau recevra la mise à jour, où 1 est le premier et 9 est le dernier.  
1. Donnez un nom à cet anneau.  
1. Fournissez une description si vous le souhaitez.  
1. Spécifiez le nombre de jours pendant lesquels la mise à jour sera déployée dans cet anneau.  
1. Spécifiez la période de test.  
1. Cliquez sur **Envoyer**.  

> [!NOTE]
> Le « Nombre de jours défini par d’autres anneaux » correspond au nombre total de jours qu’une mise à jour prendra pour s’exécuter sur tous les anneaux. Les « jours restants » indiquent le nombre maximal de jours pour *que cet* anneau se termine. La somme de « Durée du déploiement en jours » et « Période de test en jours » ne peut pas dépasser ce montant.  

**Modifier un anneau**

1. Accédez à l’onglet **Anneaux** .
1. Cliquez sur l’anneau à supprimer.  
1. Cliquez sur **Modifier l’anneau**.  
1. Modifiez le nombre de jours de déploiement et de test, si nécessaire.

**Supprimer un anneau**

1. Accédez à l’onglet **Anneaux** .  
1. Cliquez sur l’anneau à supprimer.  
1. Cliquez sur **Supprimer l’anneau**.  

> [!NOTE]
> Les anneaux par défaut ne peuvent pas être supprimés.  

**Déplacer des salles**

Le déplacement de salles d’un anneau à l’autre est possible de deux manières :

1. Accédez à l’onglet **Anneaux** .  
1. Cliquez sur l’anneau à partir duquel vous souhaitez déplacer les salles  
1. Cliquez sur **Déplacer les salles**.  
1. Sélectionnez les salles que vous souhaitez déplacer dans la **liste des salles**.  
1. Choisissez l’anneau cible vers lequel les salles sélectionnées seront déplacées dans la liste déroulante.  
1. Cliquez sur **Déplacer les salles**.  

**Ou**

1. Ouvrez les détails de la salle que vous souhaitez déplacer (via incidents, salles ou mises à jour -> salles).
1. Cliquez sur l’onglet **Mises à jour** .  
1. Sous **Anneau attribué**, cliquez sur **Modifier**.
1. Dans la liste déroulante, sélectionnez le nouvel anneau.  
1. Cliquez sur **Affecter**.

## <a name="managed-updates-visibility-and-control"></a>Mises à jour managées : visibilité et contrôle

Les services managés orchestrent les mises à jour au sein de votre organisation. Toutefois, vous disposez de la visibilité et du contrôle nécessaires pour intervenir si nécessaire. Voici les méthodes suivantes : 

- En cas d’échec d’une mise à jour, un ticket est automatiquement généré avec l’équipe Microsoft Managed Service Operations. L’équipe des opérations prendra des mesures pour corriger l’échec et vous impliquer si nécessaire.  
- Si vous voyez une mise à jour à l’origine de problèmes, vous pouvez suspendre la mise à jour avec le bouton **Suspendre** . Le fait d’appuyer sur le bouton Suspendre crée un ticket pour que le centre d’opérations examine. Veillez à fournir des détails lors de la suspension d’une mise à jour pour accélérer la réponse aux incidents.  
- Si vous voyez qu’une mise à jour a échoué dans une salle et que vous avez corrigé une raison plausible telle que la déconnexion du réseau, vous pouvez réessayer la mise à jour avec le bouton **Réessayer tous les échecs** .  
- Il peut y avoir des situations urgentes où vous pouvez décider de rendre une mise à jour disponible précédemment. Dans ce cas, vous pouvez utiliser le bouton **Forcer les mises à jour** . Lorsque vous utilisez l’option Forcer la mise à jour, vous avez le choix de forcer la mise à jour immédiatement ou lorsque la salle est disponible.  

> [!NOTE]
> **Nous ne recommandons pas de forcer les mises à jour** en tant que stratégie générale de gestion des mises à jour. Si vous envoyez (push) une mise à jour qui est toujours dans notre passe de validation, vous pouvez rencontrer des problèmes que nous connaissons déjà. Dans ce cas, la résolution des incidents pour ces salles sera effectuée de façon optimale.  

- En outre, pour garantir de bonnes pratiques de gestion des changements, nous consignerons chaque mise à jour de force en interne dans le service. À l’avenir, nous nous attendons à ce que cela soit également visible pour vous.
