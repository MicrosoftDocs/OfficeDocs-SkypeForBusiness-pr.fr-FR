---
title: Planifier les standards automatiques Teams et les files d’attente d’appels
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Découvrez les standards automatiques et les files d’attente d’appels, et comment les utiliser pour aider les appelants à parcourir un système de menus pour atteindre les personnes ou les services de votre organisation.
ms.openlocfilehash: acaa4d3e4db56b1b64869f92d27f2dfd73c4afee
ms.sourcegitcommit: 0dfe48fde767d8d9ed7bfc93684af05534acad12
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/24/2022
ms.locfileid: "69166730"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planifier les standards automatiques Teams et les files d’attente d’appels

Les standards automatiques vous permettent de configurer des options de menu pour acheminer les appels en fonction de l’entrée de l’appelant. Les options de menu d’un standard automatique, telles que « Pour les ventes, appuyez sur 1- Pour les services, appuyez sur 2 », permettent à une organisation de fournir une série de choix qui guident les appelants vers leur destination rapidement, sans avoir à recourir à un opérateur humain pour gérer les appels entrants.

Les files d’attente d’appels sont des zones d’attente pour les appelants. Dans les situations où les appelants doivent contacter une personne ayant une spécialité particulière, comme les ventes ou le service, plutôt qu’une personne spécifique, vous pouvez utiliser des files d’attente d’appels pour connecter les appelants au groupe d’agents qui peuvent les aider. Les appelants sont mis en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour prendre leur appel.

Utilisés ensemble, les standards automatiques et les files d’attente d’appels peuvent facilement acheminer les appelants vers la personne ou le service approprié de votre organisation.

## <a name="auto-attendants"></a>Les standards automatiques

L’objectif principal d’un standard automatique est de diriger un appelant vers une personne ou un service approprié en fonction de l’entrée de l’appelant dans les options de menu fournies. Les appelants peuvent être dirigés vers des personnes spécifiques au sein de votre organisation, vers des files d’attente où ils attendent de parler à l’agent disponible suivant ou vers la messagerie vocale. Différentes options de routage des appels peuvent être spécifiées pour les heures d’ouverture, les heures creuses et les jours fériés.

Les invites de menu peuvent être créées à l’aide de la synthèse vocale (invites générées par le système) ou en chargeant un fichier audio enregistré. La reconnaissance vocale accepte les commandes vocales pour la navigation mains libres, mais les personnes appelant peuvent également utiliser le clavier du téléphone pour naviguer dans les menus.

Chaque standard automatique a une langue et un fuseau horaire spécifiques. Si vous travaillez dans plusieurs langues ou plusieurs parties du monde, vous pouvez créer autant de standards automatiques différents que nécessaire pour prendre en charge vos appelants.

Pour chaque standard automatique, vous pouvez configurer un opérateur. Bien que vous puissiez configurer des appels d’opérateur pour qu’ils aillent vers différentes destinations, la fonctionnalité d’opérateur est conçue pour permettre aux appelants de parler à une personne spécifique de votre organisation qui peut les aider.

Les standards automatiques peuvent être configurés pour permettre aux appelants de rechercher dans l’annuaire de votre organisation, par nom ou par numéro de poste. Dans un standard automatique, vous pouvez spécifier qui est disponible pour la recherche dans l’annuaire en choisissant des groupes d’utilisateurs à inclure ou à exclure. (Il s’agit de *l’étendue de numérotation*.)

Les appelants peuvent atteindre un standard automatique par numéro de téléphone direct, s’il est configuré ou en étant redirigés à partir d’un autre standard automatique ou d’une file d’attente d’appels.

## <a name="call-queues"></a>Files d'attente des appels

Une file d’attente d’appels est analogue à une salle d’attente dans un bâtiment physique. Les appelants attendent en attente pendant que les appels sont routés vers les agents de la file d’attente. Les files d’attente d’appels sont couramment utilisées pour les fonctions de vente et de service. Toutefois, les files d’attente d’appels peuvent être utilisées pour toute situation où le nombre d’appels dépasse votre capacité interne, comme un réceptionniste dans une installation occupée.

Les files d’attente d’appels permettent un routage spécifique des appels dans les cas où le nombre total d’appelants dans la file d’attente ou le temps d’attente dépasse les limites que vous spécifiez. Les appels peuvent être routés vers des personnes spécifiques, une messagerie vocale, d’autres files d’attente d’appels ou des standards automatiques.

Comme les standards automatiques, les files d’attente d’appels ont chacune un paramètre de langue. Vous pouvez utiliser différentes files d’attente d’appels si vous effectuez des activités dans plusieurs langues. Les agents peuvent être membres de plusieurs files d’attente s’ils sont multilingues.

Pour chaque file d’attente d’appels, vous pouvez spécifier si les agents de la file d’attente peuvent refuser de passer des appels et si les appels doivent être acheminés vers eux en fonction de leur indication de présence dans Teams.

Vous pouvez attribuer un numéro de téléphone à une file d’attente d’appels, mais les files d’attente d’appels ne fournissent pas de routage d’appels distinct pour les heures creuses et les jours fériés. À moins que votre file d’attente d’appels ne dispose d’un personnel 24 heures sur 24, 7 jours sur 7, nous vous recommandons d’attribuer le numéro de téléphone à un standard automatique qui redirige vers la file d’attente d’appels pendant les heures d’ouverture.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer des standards automatiques et des files d’attente d’appels, vous avez besoin des ressources suivantes :

- Un [compte de ressource](manage-resource-accounts.md) pour chaque standard automatique et chaque file d’attente d’appels.
- Une [licence de compte de ressource Téléphonie Microsoft Teams](teams-add-on-licensing/virtual-user.md) gratuite pour chaque compte de ressource qui peut être directement composé à partir d’utilisateurs Teams ou de numéros de téléphone externes.
- Au moins un [numéro de service Microsoft](getting-service-phone-numbers.md), un [numéro de connexion d’opérateur](operator-connect-plan.md), un [numéro de routage direct](direct-routing-plan.md) ou un numéro hybride pour chaque compte de ressource que vous souhaitez composer directement à partir de numéros de téléphone externes.
  - Le numéro de service peut être un numéro payant ou gratuit.

> [!NOTE]
> Les comptes de ressources sont désactivés pour la connexion et doivent le rester. La conversation et la présence ne sont pas disponibles pour ces comptes.

Les agents qui reçoivent des appels des files d’attente d’appels doivent être Téléphonie – Grandes entreprises utilisateurs en ligne ou locaux activés. En outre, si les files d’attente d’appels utilisent des numéros de routage direct, les agents qui doivent conférencer ou transférer des appels ont également besoin des éléments suivants :

- Une [stratégie de routage vocal en ligne](manage-voice-routing-policies.md) affectée si la file d’attente des appels utilise le mode de transfert.
- Une [licence d’audioconférence](set-up-audio-conferencing-in-teams.md) ou une [stratégie de routage vocal en ligne](manage-voice-routing-policies.md) attribuée si la file d’attente d’appels utilise le mode conférence.

Si vos agents utilisent l’application Microsoft Teams pour les appels de file d’attente, ils doivent être en mode TeamsOnly.

Lorsque vous utilisez un compte de ressource à des fins d’ID de ligne d’appel dans les files d’attente d’appels, le compte de ressource doit disposer d’une licence de compte de ressource téléphonique Teams et de l’une des autorisations suivantes :

- Une licence [de forfait d’appels](calling-plans-for-office-365.md) et un numéro de téléphone attribué.
- Un numéro de téléphone [Operator Connect](operator-connect-plan.md) attribué.
- Une [stratégie de routage des voix en ligne](manage-voice-routing-policies.md).
  - L’attribution de numéro de téléphone est facultative lors de l’utilisation du routage direct.

Lorsqu’un standard automatique ou une file d’attente d’appels transfère des appels vers un numéro externe, les comptes de ressources spécifiques, comme indiqué ci-dessous, doivent disposer d’une licence de compte de ressource téléphonique Teams et de l’un des éléments suivants :

- Une licence [de forfait d’appels](calling-plans-for-office-365.md) et un numéro de téléphone attribué.
- Un numéro de téléphone [Operator Connect](operator-connect-plan.md) attribué.
- Une [stratégie de routage des voix en ligne](manage-voice-routing-policies.md).
  - L’attribution de numéro de téléphone est facultative lors de l’utilisation du routage direct.

Quel compte de ressource doit être sous licence :

- Attribuez une licence au compte de ressource sur le premier standard automatique recevant l’appel lorsque ce standard automatique est transféré vers d’autres standards automatiques ou files d’attente d’appels qui transfèrent des appels en externe.
- Dans tous les autres scénarios d’appel, attribuez une licence au compte de ressources du standard automatique ou de la file d’attente des appels effectuant le transfert externe.

> [!NOTE]
> Si le forfait d’appels affecté au compte de ressource est désactivé ou supprimé, [les crédits de communication](what-are-communications-credits.md), s’ils sont disponibles dans le locataire (sans être affectés au compte de ressource), sont consommés. S’il n’y a pas de forfait d’appels ou de crédits de communication, l’appel échoue.
>
> Les numéros de service de routage direct pour les standards automatiques et les files d’attente d’appels sont pris en charge uniquement pour les utilisateurs et les agents d’appel Microsoft Teams.
> 
> Les transferts entre forfait d’appels, connexion d’opérateur et jonctions de routage direct ne sont pas pris en charge.
> 
> Dans un scénario hybride, le compte de ressource doit être créé localement. Pour plus d’informations, consultez [Planifier les files d’attente d’appels cloud](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Décisions de l’entreprise

Avant de configurer vos standards automatiques et vos files d’attente d’appels, vous devez prendre certaines décisions concernant l’utilisation de ces fonctionnalités dans votre entreprise. Ces décisions déterminent les paramètres que vous choisissez lorsque vous configurez vos standards automatiques et vos files d’attente d’appels.

Documentez vos réponses à ces questions et fournissez les informations à l’administrateur qui effectue la configuration.

- De quelles langues avez-vous besoin ? Où ces langues sont-elles nécessaires - quel service ou groupe ?
- Voulez-vous autoriser les entrées vocales des appelants ou uniquement les entrées de numérotation ?
- Avez-vous besoin d’un routage d’appel distinct pour les heures creuses ou les jours fériés ? Quelles sont les heures et les jours fériés ?
- Voulez-vous autoriser les agents d’une file d’attente d’appels à refuser la prise d’appels ?
- Voulez-vous que les agents de vos files d’attente d’appels ou votre opérateur aient un ID d’appelant spécifique s’ils composent ?
- Voulez-vous activer le [stationnement et la récupération des appels](call-park-and-retrieve.md) dans votre organisation pour faciliter les transferts d’appels entre des personnes ou des services ?
- Pour les invites vocales, voulez-vous enregistrer votre propre voix ou utiliser la voix générée par le système ?
  - La voix générée par le système est facile à mettre à jour.

## <a name="technical-decisions"></a>Décisions techniques

Lorsque vous utilisez des standards automatiques et des files d’attente d’appels pour connecter des appelants à des personnes de votre organisation, vous devez prendre certaines décisions techniques avant de commencer la configuration.

Les agents peuvent être ajoutés aux files d’attente d’appel des manières suivantes :

- Utilisateurs individuels
- Listes de distribution
- Groupes de sécurité, y compris les groupes de sécurité à extension messagerie
- Groupes Microsoft 365 ou Teams

Vous pouvez utiliser une combinaison de ces options pour chaque file d’attente si nécessaire. Les groupes qui ont une adresse e-mail peuvent être utilisés pour la messagerie vocale. L’utilisation de Teams offre de nombreux avantages, notamment le stockage de fichiers partagés et la conversation entre les agents, une boîte aux lettres commune où les messages vocaux peuvent être reçus et une plateforme extensible qui peut inclure l’intégration à vos applications métier ou à Power Apps.

Nous vous recommandons de choisir une stratégie pour ajouter des agents d’appel aux files d’attente avant de commencer votre configuration.

Si vous disposez d’une infrastructure de standard automatique et de file d’attente d’appels et que vous migrez vers Teams, vous aurez besoin d’un plan pour transférer vos numéros de téléphone existants vers les nouveaux standards automatiques et files d’attente d’appels. Vous devrez peut-être créer une [commande de transfert](phone-number-calling-plans/port-order-overview.md) pour déplacer vos numéros d’un autre fournisseur. Nous vous recommandons d’acquérir temporairement un ou plusieurs nouveaux numéros de téléphone et de tester vos flux de standard automatique et de file d’attente d’appels avant de les basculer sur les numéros que vous avez actuellement en service.

**Le mode conférence** est une option dans les files d’attente d’appels qui réduit considérablement le temps nécessaire pour connecter les appels VOIP Teams et les appels RTC à un agent. Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :

- La dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS.
- système téléphonique Microsoft version 1449/1.0.94.2020051601 ou ultérieure.
  
Définissez les comptes Teams des agents sur le mode Teams uniquement. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels.

Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.

**Les plans de flux de routage** des appels permettent de déterminer le routage le plus efficace pour les personnes appelant dans votre organisation. Pour savoir comment planifier votre flux de routage des appels, consultez [Planifier votre flux de routage des appels](plan-your-call-routing-flow.md).

## <a name="getting-started"></a>Prise en main

Une fois que vous avez terminé les tâches de planification de cet article, procédez comme suit pour configurer vos standards automatiques et vos files d’attente d’appels :

1. Obtenez les numéros de service dont vous avez besoin pour les standards automatiques et les files d’attente d’appels auxquels vous souhaitez accéder en composant une numérotation directe à partir de l’extérieur de votre organisation. Cela peut inclure [le transfert de numéros d’un autre fournisseur](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou la [demande de nouveaux numéros de service](getting-service-phone-numbers.md).

2. Obtenez une [licence de compte de ressource téléphone Teams](teams-add-on-licensing/virtual-user.md) pour chaque compte de ressource que vous envisagez de créer. Ces licences étant gratuites, nous vous suggérons d’obtenir quelques licences supplémentaires si vous décidez d’apporter des modifications à vos comptes de ressources à l’avenir.

3. [Créez un compte de ressource](manage-resource-accounts.md) pour chaque standard automatique et file d’attente d’appels que vous souhaitez créer. Attribuez une licence de compte de ressource de téléphone Teams à chaque compte de ressource pouvant être appelé directement et, éventuellement, un numéro de service.

4. [Créez les jours fériés](set-up-holidays-in-teams.md) pour lesquels vous souhaitez disposer d’un routage d’appel distinct dans vos standards automatiques.

5. Si vous le souhaitez, [configurez le stationnement et la récupération des appels](call-park-and-retrieve.md) si vous souhaitez utiliser cette fonctionnalité pour faciliter les transferts d’appels.

6. Créez les groupes que vous souhaitez utiliser pour contenir les agents d’appel pour les files d’attente d’appels.

7. Si vous envisagez d’autoriser la numérotation par extension, vérifiez que vous avez ajouté le numéro de poste de vos utilisateurs à leur profil Azure Active Directory (Azure AD).

Une fois que vous avez effectué les étapes ci-dessus, vous êtes prêt à créer vos standards automatiques et vos files d’attente d’appels. Étant donné que les standards automatiques et les files d’attente d’appels peuvent rediriger les appels les uns vers les autres, reportez-vous au diagramme de flux de travail que vous avez créé pour déterminer le standard automatique ou la file d’attente d’appels qui doit être créé en premier. Dans l’exemple du diagramme ci-dessus, vous créez les files d’attente d’appels de vente et de support avant de créer le standard automatique principal Contoso, car le standard automatique principal doit diriger les appelants vers les files d’attente d’appels de vente et de support.

Pour plus d’informations sur la création de standards automatiques et de files d’attente d’appels, consultez les articles suivants :

- [Configurer un standard automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md)

> [!IMPORTANT]
> Le jeton GUID Azure AD d’un utilisateur est stocké dans le cadre de la configuration du standard automatique ou de la file d’attente d’appels lorsque l’utilisateur est configuré comme suit :
>
>  - un standard automatique ou une file **d’attente d’appels Utilisateur autorisé**.
>  - **un opérateur** de standard automatique.
>  - **personne dans le point de transfert de l’organisation**.
>  - un membre individuel d’une file d’attente d’appels.
> 
> Les configurations du standard automatique et de la file d’attente d’appels ne sont pas synchronisées avec les événements de cycle de vie Azure AD.  Les administrateurs Teams doivent mettre à jour manuellement les configurations de standard automatique et de file d’attente d’appel pour supprimer ces données personnelles lorsqu’un utilisateur inclus dans la configuration quitte l’organisation.
>
> Cela ne s’applique pas aux appartenances d’agent de file d’attente d’appel configurées via des listes de distribution ou des canaux. Elle ne s’applique pas non plus aux utilisateurs qui sont contactés par le biais de la fonctionnalité **Composer par nom** ou **Composer par numéro** des standards automatiques.

Si vous avez besoin de fonctionnalités plus étendues, telles que l’intégration avec des workflows, des bots et des SMS, envisagez [Azure Communication Services](/azure/communication-services/overview).

## <a name="related-topics"></a>Rubriques connexes

[Planifier le routage direct](direct-routing-plan.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
