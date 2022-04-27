---
title: Planifier Teams standards automatiques et les files d’attente d’appels
author: CarolynRowe
ms.author: crowe
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
description: Découvrez les standards automatiques et les files d’attente d’appels et comment les utiliser pour aider les appelants à se déplacer dans un système de menus pour atteindre les personnes ou les services de votre organisation.
ms.openlocfilehash: 76755e722abdcde6673baac42681697165921aca
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059275"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planifier Teams standards automatiques et les files d’attente d’appels

Les standards automatiques vous permettent de configurer des options de menu pour router les appels en fonction de l’entrée de l’appelant. Options de menu, telles que « Pour les ventes, appuyez sur 1.  Pour les services, appuyez sur 2 », car un standard automatique permet à une organisation de fournir une série de choix qui guident rapidement les appelants vers leur destination, sans compter sur un opérateur humain pour gérer les appels entrants.

Les files d’attente d’appels sont des zones d’attente pour les appelants. Pour les situations où les appelants doivent contacter une personne ayant une spécialité particulière , comme les ventes ou le service, plutôt qu’une personne spécifique, vous pouvez utiliser des files d’attente d’appels pour connecter les appelants au groupe d’agents qui peuvent les aider. Les appelants sont mis en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour prendre leur appel.

Utilisés ensemble, les standards automatiques et les files d’attente d’appels peuvent facilement acheminer les appelants vers la personne ou le service approprié dans votre organisation.

## <a name="auto-attendants"></a>Les standards automatiques

L’objectif principal d’un standard automatique est de diriger un appelant vers une personne ou un service approprié en fonction de l’entrée de l’appelant aux options de menu fournies. Les appelants peuvent être dirigés vers des personnes spécifiques au sein de votre organisation, pour appeler des files d’attente où ils attendent de parler à l’agent disponible suivant ou à la messagerie vocale. Différentes options de routage des appels peuvent être spécifiées pour les heures d’ouverture, les heures creuses et les jours fériés.

Les invites de menu peuvent être créées à l’aide de la synthèse vocale (invites générées par le système) ou en chargeant un fichier audio enregistré. La reconnaissance vocale accepte les commandes vocales pour la navigation mains libres, mais les personnes qui appellent peuvent également utiliser le clavier téléphonique pour naviguer dans les menus.

Chaque standard automatique a un langage et un fuseau horaire spécifiques. Si vous faites des affaires dans plusieurs langues ou dans plusieurs régions du monde, vous pouvez créer autant de standards automatiques que nécessaire pour prendre en charge vos appelants.

Pour chaque standard automatique, vous pouvez configurer un opérateur. Bien que vous puissiez configurer des appels d’opérateur pour accéder à différentes destinations, la fonctionnalité d’opérateur est conçue pour permettre aux appelants de communiquer avec une personne spécifique de votre organisation qui peut les aider.

Les standards automatiques peuvent être configurés pour permettre aux appelants de rechercher dans le répertoire de votre organisation, par nom ou par numéro d’extension. Dans un standard automatique, vous pouvez spécifier qui est disponible pour la recherche d’annuaire en choisissant des groupes d’utilisateurs à inclure ou exclure. (Il s’agit de *l’étendue de numérotation*.)

Les appelants peuvent atteindre un standard automatique par numéro de téléphone direct, s’ils sont configurés, ou en étant redirigés à partir d’un autre standard automatique ou d’une file d’attente d’appels.

## <a name="call-queues"></a>Files d'attente des appels

Une file d’attente d’appels est analogue à une salle d’attente dans un bâtiment physique. Les appelants attendent en attente pendant que les appels sont acheminés vers les agents de la file d’attente. Les files d’attente d’appels sont couramment utilisées pour les fonctions de vente et de service. Toutefois, les files d’attente d’appels peuvent être utilisées pour n’importe quelle situation où le nombre d’appels dépasse votre capacité interne, comme un receptionniste dans un établissement occupé.

Les files d’attente d’appels permettent un routage spécifique des appels dans les cas où le nombre total d’appelants dans la file d’attente ou le temps d’attente dépasse les limites que vous spécifiez. Les appels peuvent être acheminés vers des personnes spécifiques, une messagerie vocale, d’autres files d’attente d’appels ou des standards automatiques.

Comme les standards automatiques, les files d’attente d’appels ont chacune un paramètre de langue. Vous pouvez utiliser différentes files d’attente d’appels si vous faites des affaires dans plusieurs langues. Les agents peuvent être membres de plusieurs files d’attente s’ils sont multilingues.

Pour chaque file d’attente d’appels, vous pouvez spécifier si les agents de la file d’attente peuvent refuser de prendre des appels et si les appels doivent être routés vers eux en fonction de leur indication de présence dans Teams.

Vous pouvez affecter un numéro de téléphone à une file d’attente d’appels, mais les files d’attente d’appels ne fournissent pas de routage d’appels distinct pendant les heures creuses et les jours fériés. À moins que votre file d’attente d’appels ne dispose d’un personnel 24 heures sur 24 et 7 jours sur 7, nous vous recommandons d’attribuer le numéro de téléphone à un standard automatique qui redirige vers la file d’attente des appels pendant les heures d’ouverture.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer des standards automatiques et des files d’attente d’appels, vous avez besoin des ressources suivantes :

- Un compte de ressource pour chaque standard automatique et chaque file d’attente d’appels
- Une licence Téléphone Microsoft System - Virtual User gratuite pour chaque compte de ressource
- Au moins un [numéro de service Microsoft](getting-service-phone-numbers.md), un numéro Operator Connect, un numéro de routage direct ou un numéro hybride pour chaque compte de ressource que vous souhaitez être directement accessible en numérotation
 - Le numéro de service peut être un numéro payant ou gratuit

> [!NOTE]
> Les comptes de ressources sont désactivés pour la connexion et doivent le rester. La conversation et la présence ne sont pas accessibles pour ces comptes.

Les agents qui reçoivent des appels à partir des files d’attente d’appels doivent être Voix Entreprise activés en ligne ou sur site. En outre, si les files d’attente d’appels utilisent des numéros de routage direct, les agents qui doivent téléconférencer ou transférer des appels nécessitent également :

- Stratégie de routage vocal en ligne affectée si la file d’attente d’appels utilise le mode de transfert
- Une licence d’audioconférence ou une stratégie de routage vocal en ligne affectée si la file d’attente d’appels utilise le mode conférence

Si vos agents utilisent l’application Microsoft Teams pour les appels de file d’attente d’appels, ils doivent être en mode TeamsOnly.

Lors de l’utilisation d’un compte de ressource à des fins d’ID de ligne d’appel dans des files d’attente d’appels ou lorsqu’un standard automatique ou une file d’attente d’appels transfère des appels vers un numéro de téléphone externe, le compte de ressource doit disposer d’une licence d’utilisateur virtuel Système téléphonique et de l’une des options suivantes :

- Une licence [de forfait d’appels](calling-plans-for-office-365.md) et un numéro de téléphone attribué
- Un [numéro de téléphone Operator Connect](operator-connect-plan.md) attribué
- Une [stratégie de routage vocal en ligne](manage-voice-routing-policies.md) (l’attribution de numéros de téléphone est facultative lors de l’utilisation du routage direct)

> [!NOTE]
> Si le plan d’appel affecté au compte de ressource est désactivé ou supprimé, les [crédits de communication](what-are-communications-credits.md), s’ils sont disponibles dans le locataire (sans être affectés au compte de ressource), sont consommés. S’il n’y a pas de forfait d’appels ou de crédits de communication, l’appel échoue.
>
> Les numéros de service de routage direct pour le standard automatique et les files d’attente d’appels sont pris en charge uniquement pour les utilisateurs Microsoft Teams et les agents d’appel.
> 
> Les transferts entre le plan d’appel, le Operator Connect et les jonctions de routage direct ne sont pas pris en charge.
> 
> Dans un scénario hybride, le compte de ressource doit être créé localement. Pour plus d’informations, consultez [Planifier les files d’attente d’appels cloud](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Décisions d’entreprise

Avant de configurer vos standards automatiques et vos files d’attente d’appels, vous devez prendre certaines décisions concernant l’utilisation de ces fonctionnalités dans votre entreprise. Ces décisions déterminent les paramètres que vous choisissez lorsque vous configurez vos standards automatiques et les files d’attente d’appels.

Documentez vos réponses à ces questions et fournissez les informations à l’administrateur qui effectue la configuration.

- De quelles langues avez-vous besoin ? Où ces langues sont-elles nécessaires , quel service ou quel groupe ?
- Voulez-vous autoriser les entrées vocales des appelants ou uniquement les entrées de numérotation ?
- Avez-vous besoin d’un routage d’appels distinct pour les heures creuses ou les jours fériés ? Quelles sont les heures et les jours fériés ?
- Voulez-vous autoriser les agents d’une file d’attente d’appels à refuser de passer des appels ?
- Voulez-vous que les agents de vos files d’attente d’appels ou votre opérateur aient un ID d’appelant spécifique s’ils composent ?
- Voulez-vous activer le [stationnement et la récupération des appels](call-park-and-retrieve.md) dans votre organisation pour faciliter les transferts d’appel entre les personnes ou les services ?
- Pour les invites vocales, voulez-vous enregistrer la vôtre ou utiliser la voix générée par le système ? (La voix générée par le système est facile à mettre à jour.)

## <a name="technical-decisions"></a>Décisions techniques

Lorsque vous utilisez des standards automatiques et des files d’attente d’appels pour connecter des appelants à des personnes de votre organisation, il existe des décisions techniques à prendre avant de commencer la configuration.

Les agents peuvent être ajoutés aux files d’attente d’appels des manières suivantes :

- Utilisateurs individuels
- Listes de distribution
- Groupes de sécurité, y compris les groupes de sécurité à extension messagerie
- Groupes Microsoft 365 ou Teams

Vous pouvez utiliser une combinaison de ces options pour chaque file d’attente si nécessaire. Les groupes qui ont une adresse e-mail peuvent être utilisés pour la messagerie vocale. L’utilisation de Teams offre de nombreux avantages, notamment le stockage de fichiers partagés et la conversation entre agents, une boîte aux lettres commune où les messages vocaux peuvent être reçus et une plateforme extensible qui peut inclure l’intégration à vos applications métier ou Power Apps.

Nous vous recommandons de choisir une stratégie pour ajouter des agents d’appel aux files d’attente avant de commencer votre configuration.

Si vous disposez d’un standard automatique et d’une infrastructure de file d’attente d’appels et que vous migrez vers Teams, vous aurez besoin d’un plan pour transférer vos numéros de téléphone existants vers les nouveaux standards automatiques et les files d’attente d’appels. Vous devrez peut-être créer une [commande de port](phone-number-calling-plans/port-order-overview.md) pour déplacer vos numéros à partir d’un autre fournisseur. Nous vous recommandons d’acquérir temporairement un ou plusieurs nouveaux numéros de téléphone et de tester vos flux de standard automatique et de file d’attente d’appels avant de les remplacer par les numéros que vous utilisez actuellement.

*Le mode conférence* est une option dans les files d’attente d’appels qui réduit considérablement le temps nécessaire pour se connecter Teams appels VOIP et appels RTC à un agent. Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :

- la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS
- Téléphone Microsoft System version 1449/1.0.94.2020051601 ou ultérieure
  
Définissez les comptes Teams des agents en mode Teams uniquement. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels.

Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.

## <a name="plan-your-call-routing-flow"></a>Planifier votre flux de routage des appels

Dans le cadre du processus de planification, nous vous recommandons d’effectuer le routage des appels pour votre organisation dans un diagramme. Le diagramme permet de déterminer le routage le plus efficace pour les personnes qui appellent à votre organisation. Vous pouvez également utiliser le diagramme pour déterminer les standards automatiques et les files d’attente d’appels que vous devez créer, ainsi que les exigences associées, telles que les numéros de service, les licences et les comptes de ressources.

Examinons comment les standards automatiques et les files d’attente d’appels routent les appels.

Les standards automatiques routent tous les appels de l’une des manières suivantes :

- **Rediriger immédiatement** : les appels peuvent être redirigés vers l’une des destinations de routage des appels (répertoriées ci-dessous) immédiatement après avoir répondu ou après un message d’accueil initial.
- **Redirection basée sur les options de numérotation** : les appelants peuvent choisir entre les options affectées aux numéros sur leur clavier téléphonique, 0-9. Une destination de routage d’appel peut être affectée à chaque clé de numérotation.
- **Composer des personnes par nom ou par extension** : les appelants peuvent être dirigés vers le numéro d’extension de la personne qu’ils tentent d’atteindre dans le répertoire de votre organisation, ou en orthographiant le nom de la personne.
- **Déconnexion** : un standard automatique peut raccrocher l’appel.

> [!NOTE]
> Un standard automatique unique ne peut prendre en charge qu’une seule méthode « dial by ».  Pour permettre aux appelants de composer par nom et par numéro, vous devez créer un standard automatique qui a une option de numérotation par nom et l’autre pour composer par extension.  Chacune de ces options est acheminée vers des standards automatiques distincts configurés pour ces scénarios de « numérotation par ».

Lorsque les appels sont redirigés par un standard automatique ou une file d’attente d’appels, vous pouvez choisir parmi les destinations de routage des appels suivantes :

- **Personne de l’organisation** : une personne de votre organisation qui est en mesure de recevoir des appels vocaux. Il peut s’agir d’un utilisateur en ligne ou d’un utilisateur hébergé localement à l’aide de Skype Entreprise Server.
- **Application vocale** : un autre standard automatique ou une file d’attente d’appels. Choisissez le compte de ressource associé à la destination.
- **Numéro de téléphone externe** : n’importe quel numéro de téléphone. (Consultez [les détails techniques du transfert externe](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Messagerie vocale** : boîte aux lettres vocale associée à un groupe Microsoft 365 que vous spécifiez. Vous pouvez choisir si vous voulez des transcriptions de messagerie vocale et le message « Veuillez laisser un message après le ton ». invite système.
- **Opérateur** (standard automatique uniquement) : opérateur défini pour le standard automatique. La définition d’un opérateur est facultative. Un opérateur peut être l’une des autres destinations de cette liste.

Les standards automatiques offrent des options de routage d’appels distinctes pour les appels reçus en dehors des heures de bureau et pendant les jours fériés. 

Les files d’attente d’appels mettent l’appelant en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour prendre son appel. Il existe deux situations où un appelant peut être dirigé hors de la file d’attente :

- **Dépassement** des appels : si le nombre d’appels dans la file d’attente dépasse la limite que vous avez définie, les nouveaux appelants sont redirigés hors de la file d’attente.
- **Délai d’expiration** des appels : si un appelant est dans la file d’attente depuis plus longtemps que le paramètre de délai d’expiration configuré, il est redirigé hors de la file d’attente.

Les appels redirigés hors d’une file d’attente peuvent être envoyés à l’une des destinations de routage des appels répertoriées ci-dessus, à l’exception d’un opérateur. (Les files d’attente d’appels n’ont pas d’opérateurs, mais vous pouvez rediriger les appelants vers la même destination qu’un opérateur que vous avez configuré pour un standard automatique.)

L’exemple ci-dessous montre un exemple de routage des appels à l’aide de standards automatiques et de files d’attente d’appels.

![Diagramme du routage des appels à l’aide de standards automatiques et de files d’attente d’appels.](media/attendant-and-queue-call-routing.png)

Dans l’exemple ci-dessus :

- La touche zéro (0) redirige les appelants vers un opérateur. L’opérateur de ce standard automatique a été configuré en tant que **personne de l’organisation**.
- La seule clé (1) redirige les appelants vers la file d’attente des appels commerciaux. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe commerciale affectée à la file d’attente.
- Les deux (2) touches redirigent les appelants vers la file d’attente des appels de support. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe de support affectée à l’équipe.
- La file d’attente d’appels de support a un numéro de téléphone direct via un standard automatique intermédiaire. Le fait de disposer d’un standard automatique pour répondre à la ligne de support permet de séparer les heures creuses et le routage des appels de congés.
- La touche trois (3) redirige les utilisateurs vers un autre standard automatique pour l’annuaire de l’entreprise. Le standard automatique de l’annuaire de l’entreprise permet aux appelants d’appeler des personnes de l’organisation en composant leur nom ou extension.

Nous vous recommandons de créer un ou plusieurs diagrammes similaires à celui ci-dessus pour mapper le routage de vos appels. Veillez à inclure les éléments suivants dans votre diagramme ou dans la documentation associée :

- Quels standards automatiques auront un accès direct via des numéros de téléphone ?
- Quelles sont les exigences de routage des heures creuses et des congés pour chaque standard automatique ?
- Appartenance à chaque file d’attente d’appels. (Vous pouvez ajouter des utilisateurs individuellement ou mapper la file d’attente à différents types de groupes. Le mappage d’une file d’attente à une équipe offre l’expérience la plus polyvalente.)

Voici quelques bonnes pratiques de routage des appels :

- Examinez votre système d’appel existant et analysez les types et la fréquence des appels entrants. Utilisez ces informations pour informer votre standard automatique et la structure de la file d’attente des appels.
- Placez les options les plus courantes le plus tôt possible dans le menu pour router les appels le plus rapidement possible.
- Évitez de connecter les numéros de service directement aux files d’attente d’appels, sauf si les files d’attente sont disponibles 24h/24 et 7 j/7. Les files d’attente d’appels n’autorisent pas la gestion distincte des appels pendant les heures creuses ou les jours fériés. Si vous souhaitez avoir une file d’attente avec un numéro direct, affectez le numéro à un standard automatique qui redirige automatiquement vers la file d’attente pendant les heures d’ouverture.
- Si vous recevez de nombreux appels demandant des informations de base sur votre entreprise, telles que les heures d’ouverture, l’emplacement ou l’adresse du site web, envisagez de créer un standard automatique pour répondre à ces questions avec des messages enregistrés.
- Conservez la liste des éléments de menu sur cinq ou moins. Les appelants peuvent avoir du mal à mémoriser plus de cinq options. Utilisez des standards automatiques imbriqués si d’autres options sont nécessaires pour acheminer correctement un appel.
- Décrivez d’abord le service, suivi de l’option d’appui (par exemple: For Sales press 1) plutôt que l’inverse (par exemple. Appuyez sur 1 pour Ventes).
- La terminologie utilisateur que vos appelants comprendront plutôt que ce que vous pouvez utiliser en interne.
- Évitez les mises à jour fréquentes pour le routage des appels. Si vous modifiez les options de menu d’un standard automatique à l’avenir, appelez-le dans les invites vocales pour les 30 premiers jours.

## <a name="getting-started"></a>Prise en main

Une fois que vous avez terminé les tâches de planification décrites dans cet article, procédez comme suit pour configurer vos standards automatiques et vos files d’attente d’appels :

1. Obtenez les numéros de service dont vous avez besoin pour les standards automatiques et les files d’attente d’appels que vous souhaitez rendre accessibles en effectuant une numérotation directe à partir de l’extérieur de votre organisation. Cela peut inclure [le transfert de numéros à partir d’un autre fournisseur](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [la demande de nouveaux numéros de service](getting-service-phone-numbers.md).

2. Obtenez une [Système téléphonique - Licence d’utilisateur virtuel](teams-add-on-licensing/virtual-user.md) pour chaque compte de ressource que vous prévoyez de créer. Ces licences étant gratuites, nous vous suggérons d’en obtenir quelques-unes supplémentaires au cas où vous décideriez d’apporter des modifications à vos comptes de ressources à l’avenir.

3. [Créez un compte de ressource](manage-resource-accounts.md) pour chaque standard automatique et file d’attente d’appels que vous souhaitez créer. Attribuez à chaque compte une Système téléphonique - Licence d’utilisateur virtuel et, éventuellement, un numéro de service.

4. [Créez les jours fériés](set-up-holidays-in-teams.md) pour lesquels vous souhaitez disposer d’un routage des appels distinct dans vos standards automatiques.

5. Si vous souhaitez utiliser cette fonctionnalité pour faciliter les transferts d’appels, vous pouvez [également configurer le stationnement et la récupération](call-park-and-retrieve.md) des appels.

6. Créez les groupes que vous souhaitez utiliser pour contenir les agents d’appel pour les files d’attente d’appels.

7. Si vous envisagez d’autoriser la numérotation par extension, vérifiez que vous avez ajouté le numéro d’extension de vos utilisateurs à leur profil Azure Active Directory.

Une fois que vous avez effectué les étapes ci-dessus, vous êtes prêt à créer vos standards automatiques et vos files d’attente d’appels. Étant donné que les standards automatiques et les files d’attente d’appels peuvent rediriger les appels les uns vers les autres, reportez-vous au diagramme de flux de travail que vous avez créé pour déterminer le standard automatique ou la file d’attente d’appels qui doit être créé en premier. Dans l’exemple du diagramme ci-dessus, vous devez créer les files d’attente d’appels de ventes et de support avant de créer le standard automatique principal de Contoso, car le standard automatique principal doit diriger les appelants vers les files d’attente d’appels de vente et de support.

Pour plus d’informations sur la création de standards automatiques et de files d’attente d’appels, consultez les articles suivants :

- [Configurer un standard automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md)

Si vous avez besoin de fonctionnalités plus étendues, telles que l’intégration aux flux de travail, aux bots et aux SMS, envisagez [Azure Communication Services](/azure/communication-services/overview).

## <a name="related-topics"></a>Sujets associés

[Planifier le routage direct](direct-routing-plan.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Créer une file d’attente d’appels - Didacticiel sur les petites entreprises](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurer un standard automatique - Didacticiel sur les petites entreprises](business-voice/create-a-phone-system-auto-attendant-smb.md)
