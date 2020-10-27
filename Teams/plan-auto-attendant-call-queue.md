---
title: Plan pour les standards automatiques d’équipe et les files d’attente d’appels
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: En savoir plus sur les standards automatiques et les files d’attente d’appels et sur leur utilisation pour permettre aux appelants de se déplacer dans un système de menus pour joindre des personnes ou des services au sein de votre organisation.
ms.openlocfilehash: 7407b9a2bbcd8d8b3fb5d15202d1bba518953f07
ms.sourcegitcommit: 6c24c77f0aad693d45dd5657c12bf876f62c495b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2020
ms.locfileid: "48765941"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Plan pour les standards automatiques d’équipe et les files d’attente d’appels

Les standards automatiques vous permettent de configurer des options de menu pour acheminer les appels en fonction de l’entrée de l’appelant. Dans les options de menu, telles que «pour les ventes, tapez 1.  Pour les services, appuyez sur 2 ", pour un standard automatique, permet à une organisation d’offrir une série d’options pour guider les appelants vers leur destination rapidement, sans compter sur un opérateur humain pour gérer les appels entrants.

Les files d’attente d’appels sont des zones d’attente pour les appelants. Pour les situations dans lesquelles les appelants doivent joindre quelqu’un ayant une spécialité particulière (par exemple, ventes ou service-plutôt qu’une personne spécifique), vous pouvez utiliser les files d’attente d’appels pour connecter les appelants au groupe d’agents qui peuvent les aider. Les appelants sont mis en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour passer leur appel.

Utilisées ensemble, les standards automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié au sein de votre organisation.

## <a name="auto-attendants"></a>Les standards automatiques

L’objectif principal d’un standard automatique est de diriger un appelant vers une personne ou un service approprié en fonction de l’entrée de l’appelant aux options de menu fournies. Les appelants peuvent être dirigés vers des personnes spécifiques au sein de votre organisation afin d’appeler des files d’attente au sein desquelles ils attendent de communiquer avec l’agent disponible suivant ou la boîte vocale. Différentes options de routage des appels peuvent être spécifiées pour les heures d’activité, les heures d’inactivité et les jours fériés.

Les invites de menu peuvent être créées à l’aide de la conversion de texte par synthèse vocale ou du téléchargement d’un fichier audio enregistré. La reconnaissance vocale accepte les commandes vocales pour la navigation mains libres, mais les personnes appelant peuvent également utiliser le clavier du téléphone pour naviguer dans les menus.

Chaque standard automatique dispose d’une langue et d’un fuseau horaire spécifiques. Si vous travaillez dans plusieurs langues ou dans plusieurs parties du monde, vous pouvez créer autant de standards automatiques que nécessaire pour prendre en charge les appelants.

Pour chaque standard automatique, vous pouvez configurer un opérateur. Même si vous pouvez configurer les appels d’opérateur pour qu’ils accèdent à un large éventail de destinations, la fonctionnalité opérateur est conçue pour permettre aux appelants de parler à une personne spécifique de votre organisation qui peut les aider.

Les standards automatiques peuvent être configurés pour permettre aux appelants de rechercher dans l’annuaire de votre organisation, par nom ou par numéro de poste. Dans un standard automatique, vous pouvez spécifier les personnes disponibles pour la recherche dans l’annuaire en choisissant des groupes d’utilisateurs à inclure ou à exclure. (Connu sous le nom de *étendue de numérotation* )

Les appelants peuvent atteindre un standard automatique par numéro de téléphone direct, s’il est configuré ou en effectuant une redirection à partir d’un autre standard automatique ou d’une file d’attente d’appels.

## <a name="call-queues"></a>Files d'attente des appels

Une file d’attente d’appels est analogue à une salle d’attente dans un bâtiment physique. Les appelants sont patienter pendant que les appels sont routés vers les agents de la file d’attente dès qu’ils sont disponibles. Les files d’attente d’appels sont couramment utilisées pour les fonctions ventes et service. En revanche, il est possible d’utiliser les files d’attente d’appels dans toutes les situations où le nombre d’appels est supérieur à votre capacité interne, par exemple une réceptionniste dans une salle de disponibilité.

Les files d’attente d’appels permettent d’acheminer des appels en particulier dans les cas où le nombre total d’appels dans la file d’attente ou le temps d’attente dépasse les limites que vous spécifiez. Les appels peuvent être routés vers des personnes spécifiques, une boîte vocale, d’autres files d’attente d’appels ou des standards automatiques.

À l’instar des standards automatiques, les files d’attente des appels disposent chacun d’un paramètre de langue. Vous pouvez utiliser d’autres files d’attente d’appels si vous travaillez dans plusieurs langues. Les agents peuvent être membres de plusieurs files d’attente s’ils sont multilingues.

Pour chaque file d’attente d’appels, vous pouvez spécifier si les agents de la file d’attente peuvent refuser de prendre des appels et si les appels doivent être routés vers eux en fonction de leur indication de présence dans Teams.

Vous pouvez affecter un numéro de téléphone à une file d’attente d’appels, mais les files d’attente d’appels ne fournissent pas un routage d’appel distinct pour les heures et les jours fériés. Sauf si votre file d’attente d’appels est 24/7, nous vous recommandons d’affecter le numéro de téléphone à un standard automatique qui redirige vers la file d’attente d’appels pendant les heures d’activité.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer des standards automatiques et des files d’attente d’appels, vous avez besoin des ressources suivantes :

- Un compte de ressources pour chaque standard automatique et chaque file d’attente d’appels
- Un système téléphonique gratuit-licence d’utilisateur virtuel pour chaque compte de ressources
- Un numéro de service pour chaque standard automatique ou file d’attente d’appels que vous voulez appeler directement
- Plan d’appel pour chaque personne recevant des appels de file d’attente d’appels

> [!NOTE]
> Les numéros de service de routage direct pour le standard automatique et les files d’attente d’appels sont uniquement pris en charge pour les utilisateurs et les appels de Microsoft Teams.

## <a name="business-decisions"></a>Prise de décision commerciale

Avant de configurer vos standards automatiques et les files d’attente d’appels, vous devez prendre des décisions concernant l’utilisation de ces fonctionnalités dans votre entreprise. Ces décisions déterminent les paramètres que vous choisissez lorsque vous configurez vos standards automatiques et les files d’attente d’appels.

Documentez vos réponses à ces questions et fournissez les informations nécessaires à l’administrateur pour la configuration.

- Quelles langues avez-vous besoin ? Où ces langues sont-elles nécessaires ? quel service ou groupe ?
- Souhaitez-vous autoriser les entrées vocales des appelants ou uniquement les entrées de numérotation ?
- Avez-vous besoin d’un routage d’appels distinct pour les heures ou jours fériés ? Quels sont les heures et les jours fériés ?
- Souhaitez-vous autoriser les agents dans une file d’attente d’appels à ne pas prendre d’appels ?
- Souhaitez-vous que les agents figurant dans vos files d’attente d’appels ou votre opérateur aient un IDENTIFIant d’appelant en particulier s’ils sont en ligne ?
- Souhaitez-vous activer le [stationnement et la récupération des appels](call-park-and-retrieve.md) au sein de votre organisation pour faciliter les appels entre personnes ou services ?
- Pour les invites vocales, voulez-vous enregistrer votre propre ou utiliser la voix générée par le système ? (La voix générée par le système est facile à mettre à jour.)

## <a name="technical-decisions"></a>Décisions techniques

Lors de l’utilisation de standards automatiques et de files d’attente d’appels pour connecter les appelants aux personnes de votre organisation, vous devez prendre des décisions techniques avant de procéder à la configuration.

Les agents peuvent être ajoutés aux files d’attente d’appels comme suit :

- Utilisateurs individuels
- Listes de distribution
- Groupes de sécurité, y compris des groupes de sécurité à extension messagerie
- Groupes ou équipes Microsoft 365

Vous pouvez utiliser une combinaison de ces options pour chaque file d’attente, le cas échéant. Les groupes disposant d’une adresse de messagerie peuvent être utilisés pour la boîte vocale. L’utilisation de teams offre de nombreux avantages, y compris le stockage de fichiers partagé et la discussion entre les agents, une boîte aux lettres commune dans laquelle les messages vocaux peuvent être reçus et une plate-forme extensible qui peut inclure l’intégration à vos applications métier ou applications Power.

Nous vous recommandons de choisir une stratégie permettant d’ajouter des agents d’appel aux files d’attente avant de commencer la configuration.

Si vous avez un standard automatique et une infrastructure de file d’attente d’appels et que vous effectuez une migration vers Teams, vous avez besoin d’un plan pour transférer vos numéros de téléphone existants vers les nouveaux standards automatiques et les files d’attente d’appels. Vous devrez peut-être créer une [demande](phone-number-calling-plans/port-order-overview.md) de transfert pour déplacer vos numéros à partir d’un autre fournisseur. Nous vous recommandons d’acquérir temporairement un ou plusieurs nouveaux numéros de téléphone et de tester votre standard automatique et d’appeler les flux de la file d’attente avant de les basculer sur les numéros déjà en service.

Le *mode conférence* est une option dans les files d’attente d’appels qui réduit considérablement le temps nécessaire pour relier les appels VoIP d’équipes et les appels RTC à un agent. Pour que le mode conférence fonctionne, les agents de la file d’attente d’appels doivent utiliser un des clients suivants :

- Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS
  - Microsoft teams Phone version 1449/1.0.94.2020051601 ou version ultérieure
  
Définissez les comptes équipes des agents sur mode équipes uniquement. Les agents qui ne satisfont pas les exigences requises ne sont pas inclus dans la liste routage des appels.

Nous vous recommandons d’activer le mode Conférence pour vos files d’attente si vos agents utilisent tous des clients compatibles.

> [!NOTE]
> Occupé sur occupé n’est pas pris en charge par le mode conférence. Les agents sur les appels hors file d’attente risquent de se présenter avec un appel de file d’attente d’appels si le routage basé sur la présence n’est pas activé.

## <a name="plan-your-call-routing-flow"></a>Planifier le flux d’acheminement des appels

Dans le cadre du processus de planification, nous vous recommandons de travailler sur le routage des appels de votre organisation dans un diagramme. Le diagramme permet de déterminer le routage le plus efficace pour les personnes appelant votre organisation. Vous pouvez également utiliser le diagramme pour identifier les standards automatiques et les files d’attente d’appels que vous devez créer, ainsi que les exigences associées, telles que les numéros de service, les licences et les comptes de ressources.

Examinons la façon dont les standards automatiques et les files d’attente d’appels sont acheminés.

Standards automatiques routez tous les appels de l’une des façons suivantes :

- **Redirection immédiate** : les appels peuvent être redirigés vers l’une des destinations de routage des appels (répertoriées ci-dessous) immédiatement après la réponse ou après un message d’accueil initial.
- **Redirection basée sur les options de numérotation** : les appelants peuvent être redirigés entre les options affectées aux numéros sur leur clavier téléphonique, 0-9. Chaque clé de numérotation est affectée à une destination de routage des appels.
- **Composer** un numéro ou une extension : les appelants peuvent être dirigés vers le numéro de poste de la personne que vous essayez d’accéder dans l’annuaire de votre organisation, ou en épelant le nom de la personne.
- **Déconnecter** : un standard automatique peut raccrocher.

> [!NOTE]
> Un standard automatique unique ne peut prendre en charge qu’une seule méthode de « numérotation ».  Pour permettre aux appelants de composer par nom et par numéro, vous devez créer un standard automatique ayant une option de numérotation par nom et l’autre pour composer par poste.  Chacune de ces options sera routée vers les différents standards automatiques configurés pour ces scénarios de « numérotation ».

Lorsque les appels sont redirigés par un standard automatique ou une file d’attente d’appels, vous pouvez choisir l’une des destinations de routage des appels suivantes :

- **Personne de votre organisation** : une personne de votre organisation qui peut recevoir des appels vocaux. Il peut s’agir d’un utilisateur en ligne ou hébergé sur site utilisant Skype entreprise Server.
- **Application vocale** -autre standard automatique ou file d’attente d’appels. Choisissez le compte de ressources associé à la destination.
- **Numéro de téléphone externe** -n’importe quel numéro de téléphone. (Voir les [Détails techniques sur les transferts externes](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- Boîte **vocale** -la boîte aux lettres vocale associée à un groupe Microsoft 365 que vous spécifiez.
- **Opérateur** (standard automatique uniquement)-l’opérateur défini pour le standard automatique. La définition d’un opérateur est facultative. Un opérateur peut être l’une des autres destinations de cette liste.

Les standards automatiques proposent des options de routage des appels distinctes pour les appels reçus en dehors des heures de travail et des jours fériés. Le routage des appels après-temps autorise toutes les options répertoriées ci-dessus, tandis que le routage des appels de vacances permet uniquement de rediriger ou déconnecter un appel, mais pas d’options de touches de numérotation.

Les files d’attente d’appels placent l’appelant en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour passer son appel. Il existe deux situations dans lesquelles un appelant peut être dirigé hors de la file d’attente :

- **Dépassement d’appel** : si le nombre d’appels dans la file d’attente dépasse la limite que vous définissez, les nouveaux appelants sont redirigés hors de la file d’attente.
- **Délai d’appel** : si un appelant se trouve dans la file d’attente au-delà du paramètre de délai d’expiration configuré, il est redirigé hors de la file d’attente.

Les appels redirigés vers une file d’attente peuvent être envoyés vers l’une des destinations de routage des appels indiquées ci-dessus, à l’exception de l’opérateur. (Les files d’attente d’appels n’ont pas d’opérateur, mais vous pouvez rediriger les appelants vers la même destination qu’un opérateur configuré pour un standard automatique.)

L’exemple ci-dessous montre un exemple de routage des appels à l’aide de standards automatiques et de files d’attente d’appels.

![Diagramme de routage des appels à l’aide de standards automatiques et de files d’attente d’appels](media/attendant-and-queue-call-routing.png)

Dans l’exemple ci-dessus :

- La clé zéro (0) redirige les appelants vers un opérateur. L’opérateur de ce standard automatique a été configuré en tant que **membre de l’organisation** .
- La clé un (1) redirige les appelants vers la file d’attente des appels commerciaux. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe commerciale affectée à la file d’attente.
- Les deux clés (2) redirigent les appelants vers la file d’attente des appels de support. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe de support technique affectée à l’équipe.
- La file d’attente des appels d’assistance a un numéro de téléphone direct via un standard automatique intermédiaire. Le fait de répondre à un standard automatique permet de répondre aux appels d’assistance.
- La clé trois (3) redirige les utilisateurs vers un autre standard automatique de l’annuaire de l’entreprise. Le standard automatique de l’annuaire de l’entreprise permet aux appelants d’appeler des personnes de l’organisation en composant leur nom ou leur extension.

Nous vous recommandons de créer un ou plusieurs diagrammes similaires à celui ci-dessus pour mapper le routage des appels. Veillez à inclure les éléments suivants dans votre diagramme ou dans la documentation associée :

- Quels standards automatiques peuvent avoir accès directement via des numéros de téléphone ?
- Quelles sont les exigences en matière de routage des heures et des vacances pour chaque standard automatique ?
- L’appartenance à chaque file d’attente d’appels. (Vous pouvez ajouter des utilisateurs individuellement ou mapper la file d’attente à différents types de groupes. Le mappage d’une file d’attente à une équipe fournit l’interface la plus polyvalente.)

Voici quelques recommandations en matière de routage des appels :

- Examinez votre système d’appel existant et analysez les types et la fréquence des appels entrants. Utilisez ces informations pour vous aider à informer votre standard automatique et la structure de la file d’attente d’appels.
- Placez les options les plus courantes dans le menu pour diriger les appels le plus rapidement possible.
- Évitez de connecter des numéros de service directement aux files d’attente, sauf si les files d’attente sont disponibles 24/7. Les files d’attente d’appels n’autorisent pas la gestion des appels séparés pour les heures ou jours fériés. Si vous souhaitez disposer d’une file d’attente avec un numéro direct, attribuez le numéro à un standard automatique qui est automatiquement redirigé vers la file d’attente pendant les heures d’activité.
- Si vous recevez de nombreux appels demandant des informations de base sur votre entreprise (par exemple, des heures de travail, un emplacement ou une adresse de site Web), envisagez de créer un standard automatique pour répondre à ces questions à l’aide de messages enregistrés.
- Conserver la liste des éléments de menu à cinq ou moins. Les appelants peuvent rencontrer des difficultés pour mémoriser plus de cinq options. Utilisez des standards automatiques imbriqués si d’autres options sont nécessaires pour acheminer correctement un appel.
- Décrivez d’abord le service, puis l’option d’appuyer sur (par exemple : pour les ventes Press 1) plutôt que dans l’autre (par exemple, Appuyez sur 1 pour les ventes.
- Terminologie utilisée par les appelants au lieu de ce que vous pouvez utiliser en interne.
- Évitez les mises à jour fréquentes du routage des appels. Si vous modifiez les options de menu de votre standard automatique à l’avenir, appelez-le dans les invites vocales pour les 30 premiers jours.

## <a name="resource-accounts-and-phone-numbers"></a>Comptes de ressources et numéros de téléphone

Teams utilise des *[comptes de ressources](manage-resource-accounts.md)* pour connecter des standards automatiques et des files d’attente d’appels entre eux et de leur affecter des numéros de téléphone le cas échéant.

- Chaque file d’attente d’appels et ce standard automatique nécessitent au moins un compte de ressources.
- Chaque compte de ressources nécessite un système téléphonique gratuit-licence utilisateur virtuelles.
- Un compte de ressource peut éventuellement être affecté à un ou plusieurs numéros de service. (C’est la façon dont les numéros de téléphone sont affectés aux standards automatiques et aux files d’attente d’appels.)

Vous pouvez affecter un numéro de [service Microsoft](getting-service-phone-numbers.md), un numéro de routage direct ou un numéro hybride à un compte de ressources.

Vous pouvez utiliser des numéros de service gratuits ou payants. Vous ne pouvez pas utiliser les numéros de téléphone des utilisateurs pour les standards automatiques ou les files d’attente d’appels.

## <a name="getting-started"></a>Prise en main

Une fois que vous avez terminé les tâches de planification décrites dans cet article, procédez comme suit pour préparer vos standards automatiques et vos files d’attente d’appels :

1. Obtenez les numéros de service dont vous avez besoin pour les standards automatiques et les files d’attente d’appels que vous souhaitez rendre accessibles en appelant directement le numéro de l’extérieur de votre organisation. Il peut s’agir [de transférer les numéros d’un autre fournisseur](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou de [demander de nouveaux numéros de service](getting-service-phone-numbers.md).

2. Obtenez un [système téléphonique-licence utilisateur virtuelles](teams-add-on-licensing/virtual-user.md) pour chaque compte de ressources que vous envisagez de créer. Ces licences étant gratuites, nous vous suggérons d’en obtenir quelques plus en cas de modification de vos comptes de ressources à l’avenir.

3. [Créez un compte de ressources](manage-resource-accounts.md) pour chaque standard automatique et file d’attente d’appels que vous souhaitez créer. Affectez à chaque compte un système téléphonique-une licence utilisateur virtuelle et éventuellement un numéro de service.

4. [Créez les jours fériés](set-up-holidays-in-teams.md) pour lesquels vous voulez que le routage des appels soit séparé dans vos standards automatiques.

5. Vous pouvez également [configurer le parking et la récupération des appels](call-park-and-retrieve.md) si vous souhaitez utiliser cette fonctionnalité pour faciliter les transferts d’appels.

6. Créez les groupes que vous souhaitez utiliser pour contenir les agents d’appel pour les files d’attente d’appels.

7. Si vous envisagez d’autoriser le numérotation par poste, assurez-vous d’avoir ajouté le numéro de poste de vos utilisateurs à leur profil Azure Active Directory.

Après avoir suivi les étapes ci-dessus, vous êtes prêt à créer vos standards automatiques et vos files d’attente d’appels. Étant donné que les standards automatiques et les files d’attente d’appels peuvent rediriger les appels entre eux, consultez le diagramme de flux de travail que vous avez créé pour déterminer le standard automatique ou la file d’attente d’appels à créer en premier. Dans l’exemple de l’illustration ci-dessus, vous pouvez créer les files d’attente des appels commerciaux et du support technique avant de créer le standard automatique principal de contoso, car le standard automatique principal doit diriger les appelants vers les files d’attente des appels commerciaux et de support.

Pour plus d’informations sur la création de standards automatiques et de files d’attente d’appels, voir les articles suivants :

- [Configurer un standard automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Sujets associés

[Planifier le routage direct](direct-routing-plan.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)
