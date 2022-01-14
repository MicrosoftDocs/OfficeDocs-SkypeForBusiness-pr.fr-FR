---
title: Planifier les appels Teams automatiques et les files d’attente d’appels
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
description: Découvrez les files d’attente et les files d’attente automatiques et comment les utiliser pour aider les appelants à se déplacer dans un système de menus pour atteindre des personnes ou des services de votre organisation.
ms.openlocfilehash: 89c799f5d42adc3367f027a1dec258ba16d97aa6
ms.sourcegitcommit: c7904086e6956ad8d0e5544530bcc90d608b6e6a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2022
ms.locfileid: "62039887"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planifier les appels Teams automatiques et les files d’attente d’appels

Les attendants automatiques vous permettent de configurer des options de menu pour router les appels en fonction de la saisie de l’appelant. Options de menu, telles que « Pour les ventes, appuyez sur 1.  Pour les Services, appuyez sur 2 ». Pour un employé automatique, une organisation fournit une série de choix qui guident les appelants vers leur destination rapidement, sans faire appel à un opérateur humain pour gérer les appels entrants.

Les files d’attente sont des zones d’attente pour les appelants. Dans les situations où les appelants doivent joindre une personne spécifique (par exemple, ventes ou service) plutôt qu’une personne en particulier, vous pouvez utiliser des files d’attente pour connecter les appelants au groupe d’agents qui peuvent les aider. Les appelants sont mis en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour prendre son appel.

Utilisées ensemble, les files d’attente automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié dans votre organisation.

## <a name="auto-attendants"></a>Les standards automatiques

L’objectif principal d’un tel service est de diriger l’appelant vers une personne ou un service approprié en fonction des entrées de l’appelant sur les options de menu proposées. Les appelants peuvent être dirigés vers des personnes spécifiques de votre organisation, vers des files d’attente jusqu’à ce qu’ils discutent avec le prochain agent disponible ou vers la messagerie vocale. Différentes options de routage des appels peuvent être spécifiées pour les heures d’ouverture, les heures d’ouverture et les jours fériés.

Vous pouvez créer des invites de menu à l’aide de la reconnaissance vocale (invites générées par le système) ou en téléchargeant un fichier audio enregistré. La reconnaissance vocale accepte les commandes vocales pour une navigation mains libres, mais les appelants peuvent également utiliser le clavier téléphonique pour naviguer dans les menus.

Chaque employé automatique dispose d’une langue et d’un fuseau horaire spécifiques. Si vous avez des activités dans plusieurs langues ou dans plusieurs régions du monde, vous pouvez créer autant de serveurs automatiques que nécessaire pour prendre en charge vos appelants.

Pour chaque attendant automatique, vous pouvez configurer un opérateur. Bien que vous pouvez configurer les appels d’opérateur pour aller vers différentes destinations, la fonctionnalité de l’opérateur est conçue pour permettre aux appelants de parler à une personne spécifique de votre organisation qui peut les aider.

Les serveurs automatiques peuvent être configurés pour permettre aux appelants d’effectuer des recherches dans l’annuaire de votre organisation, soit par nom, soit par numéro de poste. Dans un attendant automatique, vous pouvez spécifier les utilisateurs disponibles pour la recherche dans l’annuaire en choisissant les groupes d’utilisateurs à inclure ou à exclure. (Cela est connu sous le nom de *portée de numérotation*.)

Les appelants peuvent accéder à un service de téléphonie automatique par numéro de téléphone direct, s’ils sont configurés, ou redirigés à partir d’un autre moyen de service automatique ou d’une file d’attente d’appels.

## <a name="call-queues"></a>Files d'attente des appels

Une file d’attente d’appels est analogue à une salle d’attente dans un bâtiment physique. Les appelants patientent pendant que les appels sont acheminés vers les agents dans la file d’attente. Les files d’attente d’appels sont couramment utilisées pour les fonctions de vente et de service. Toutefois, les files d’attente peuvent être utilisées dans toute situation où le nombre d’appels dépasse votre capacité interne, par exemple un appelant qui se trouve dans une installation occupée.

Les files d’attente autorisent un routage spécifique des appels lorsque le nombre total d’appelants dans la file d’attente ou le temps d’attente dépasse les limites que vous spécifiez. Les appels peuvent être acheminés vers des personnes spécifiques, une messagerie vocale, d’autres files d’attente d’appels ou des files d’attente automatiques.

Comme les files d’attente automatiques, les files d’attente d’appels ont chacune un paramètre de langue. Vous pouvez utiliser des files d’attente différentes si vous utilisez plusieurs langues. Les agents peuvent être membres de plusieurs files d’attente s’ils sont multilingues.

Pour chaque file d’attente d’appels, vous pouvez spécifier si des agents dans la file d’attente peuvent refuser de prendre des appels et si les appels doivent être acheminés vers eux en fonction de leur indication de présence dans Teams.

Vous pouvez affecter un numéro de téléphone à une file d’attente d’appels, mais les files d’attente ne fournissent pas de routage des appels distincts pour les heures d’ouverture et les jours fériés. À moins que votre file d’attente d’appels ne soit qualifiée 24 heures sur 24, 7 jours sur 7, nous vous recommandons d’affecter le numéro de téléphone à un employé qui redirige vers la file d’attente pendant les heures d’ouverture.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer des files d’attente et des files d’attente automatiques, vous avez besoin des ressources suivantes :

- Un compte de ressource pour chaque employé automatique et chaque file d’attente d’appels
- Licence utilisateur Microsoft Teams Téléphone virtuel pour chaque compte de ressource
- Au moins un numéro de [service Microsoft,](getting-service-phone-numbers.md)un numéro de Connecter opérateur, un numéro de routage direct ou un numéro hybride pour chaque compte de ressource à composer directement
 - Le numéro de service peut être un numéro gratuit ou gratuit

> [!NOTE]
> Les comptes de ressources sont désactivés pour la se connecte et doivent le rester. La conversation et la présence ne sont pas disponibles pour ces comptes.

Les agents qui reçoivent des appels depuis les files d’attente d’appels Voix Entreprise les utilisateurs en ligne ou sur site. De plus, si les files d’attente d’appels utilisent des numéros de routage direct, les agents qui ont besoin de conférences ou de transferts d’appels nécessitent également :

- Stratégie de routage vocal en ligne affectée si la file d’attente d’appels utilise le mode de transfert
- Licence d’audioconférence ou stratégie de routage vocal en ligne affectée si la file d’attente d’appels utilise le mode de conférence

Si vos agents utilisent l’application Microsoft Teams pour les appels de la file d’attente d’appels, ils doivent être en mode TeamsOnly.

Lorsque vous utilisez un compte de ressource pour appeler des ID de ligne dans des files d’attente ou lorsqu’un attendant automatique ou une file d’attente d’appels transfère les appels vers un numéro de téléphone externe, le compte de ressource doit avoir une licence d’utilisateur virtuel Teams Téléphone et l’une des autorisations suivantes doit lui être attribuée :

- Licence [forfait d’appels](calling-plans-for-office-365.md) et numéro de téléphone affecté
- Un [opérateur Connecter](operator-connect-plan.md) numéro de téléphone affecté
- Une [stratégie de routage vocal en ligne](manage-voice-routing-policies.md) (l’affectation de numéros de téléphone est facultative lors de l’utilisation du routage direct)

> [!NOTE]
> Si le plan d’appels affecté au compte de ressource est désactivé ou supprimé, les [crédits](what-are-communications-credits.md)de communication, s’ils sont disponibles dans le client (sans être affectés au compte de ressource), sont consommées. S’il n’y a pas de plan d’appel ou de crédits de communication, l’appel échouera.
>
> Les numéros de service de routage direct pour le support automatique et les files d’attente d’appels sont pris en charge Microsoft Teams et les agents d’appel uniquement.
> 
> Les transferts entre le plan d’appel, Connecter ligne d’opérateur et les ligne de routage direct ne sont pas pris en charge.
> 
> Dans un scénario hybride, le compte de ressource doit être créé en local. Pour plus d’informations, voir [Planifier les files d’attente dans le cloud.](/skypeforbusiness/hybrid/plan-call-queue)

## <a name="business-decisions"></a>Décisions d’entreprise

Avant de configurer vos files d’attente et les files d’attente automatiques, vous devez prendre certaines décisions sur l’utilisation de ces fonctionnalités dans votre entreprise. Ces décisions déterminent les paramètres que vous choisissez lorsque vous configurez vos files d’attente et les files d’attente automatiques.

Documentez vos réponses à ces questions et fournissez les informations à l’administrateur lors de la configuration.

- Quelles sont les langues dont vous avez besoin ? Où ces langues sont-elles nécessaires (service ou groupe) ?
- Voulez-vous autoriser les entrées vocales des appelants ou uniquement les entrées de numérotation ?
- Vous avez besoin d’un routage d’appel distinct pour les heures d’ouverture et les jours fériés ? Que sont les heures et les jours fériés ?
- Voulez-vous autoriser les agents d’une file d’attente d’appels à ne plus prendre d’appels ?
- Voulez-vous que les agents dans vos files d’attente d’appels ou votre opérateur ont un ID d’appelant spécifique s’ils se sont sortants ?
- Voulez-vous activer le [parc](call-park-and-retrieve.md) d’appels et la récupération dans votre organisation pour faciliter les remises d’appels entre des personnes ou des services ?
- Pour les invites vocales, voulez-vous enregistrer votre propre voix ou utiliser la voix générée par le système ? (La voix générée par le système est facile à mettre à jour.)

## <a name="technical-decisions"></a>Décisions techniques

Lorsque vous utilisez des files d’attente et des files d’attente automatiques pour connecter des appelants à des personnes de votre organisation, vous devez prendre certaines décisions techniques avant de commencer la configuration.

Des agents peuvent être ajoutés aux files d’attente des appels des façons suivantes :

- Utilisateurs individuels
- Listes de distribution
- Groupes de sécurité, y compris les groupes de sécurité à messagerie électronique
- Microsoft 365 groupes ou groupes Teams

Vous pouvez utiliser une combinaison de ces options pour chaque file d’attente si nécessaire. Les groupes qui ont une adresse de messagerie peuvent être utilisés pour la messagerie vocale. L’utilisation de Teams offre de nombreux avantages, notamment un stockage de fichiers partagés et des échanges entre agents, une boîte aux lettres commune où les messages vocaux peuvent être reçus et une plateforme extensible qui peut inclure l’intégration à vos applications métier ou à vos Power Apps.

Nous vous recommandons de choisir une stratégie pour ajouter des agents d’appel aux files d’attente avant de commencer votre configuration.

Si vous avez déjà un service de service automatique et une infrastructure de files d’attente d’appels et que vous migrez vers Teams, vous avez besoin d’un plan pour transférer vos numéros de téléphone existants vers les nouveaux travailleurs automatiques et les nouvelles files d’attente d’appels. Vous devrez peut-être créer une [commande de port](phone-number-calling-plans/port-order-overview.md) pour déplacer vos numéros à partir d’autres fournisseurs. Nous vous recommandons d’acheter temporairement un ou plusieurs nouveaux numéros de téléphone et de tester le flux de votre service de service automatique et de la file d’attente d’appels avant de les remplacer par les numéros en cours de service.

*Le mode* conférence est une option dans les files d’attente d’appels qui réduit de façon significative la durée de connexion Teams appels VOIP et PSTN à un agent. Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :

- la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS
- Microsoft Teams Téléphone version 1449/1.0.94.2020051601 ou ultérieure
  
Définissez le mode Teams comptes de l’agent Teams’utilisateur. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels.

Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.

## <a name="plan-your-call-routing-flow"></a>Planifier le flux de routage des appels

Dans le cadre du processus de planification, nous vous recommandons d’organiser le routage des appels pour votre organisation dans un diagramme. Le diagramme vous aide à déterminer le routage le plus efficace pour les personnes appelant dans votre organisation. Vous pouvez également utiliser le diagramme pour déterminer les normes automatiques et les files d’attente d’appels que vous devez créer, ainsi que les exigences associées telles que les numéros de service, les licences et les comptes de ressources.

Voyons comment les attendants automatiques et les files d’attente d’appels routent les appels.

Les attendants automatiques routent tous les appels de l’une des façons suivantes :

- **Redirection immédiate** : les appels peuvent être redirigés vers l’une des destinations de routage des appels (répertoriées ci-dessous) dès la réponse ou après une salutation initiale.
- **Rediriger en fonction des options** de numérotation : les appelants peuvent être redirigés vers les options qui sont affectées aux numéros sur leur clavier téléphonique, 0-9. Chaque clé de numérotation peut être affectée à une destination de routage des appels.
- Composer le **numéro** des personnes par nom ou numéro de poste : les appelants peuvent être dirigés vers le numéro de poste de la personne qu’ils tentent de joindre dans l’annuaire de votre organisation, ou en orthographiant le nom de la personne.
- **Déconnexion** : un attendant automatique peut raccrocher.

> [!NOTE]
> Un seul moyen de traitement automatique ne peut prendre en charge qu’une seule méthode de numérotation par téléphone.  Pour autoriser les appelants à composer par nom et numéro, vous devrez créer un moyen de numérotation automatique avec une option de numérotation par nom et l’autre pour la numérotation par numéro de poste.  Chacune de ces options route vers des itinéraires automatiques distincts configurés pour ces scénarios de « numérotation par ».

Lorsque les appels sont redirigés par un agent automatique ou une file d’attente d’appels, vous avez le choix entre les destinations de routage suivantes :

- **Une personne de l’organisation,** une personne de votre organisation qui peut recevoir des appels vocux. Il peut s’agit d’un utilisateur en ligne ou d’un utilisateur hébergé sur site à l’aide d Skype Entreprise Server.
- **Application vocale :** un autre attendant automatique ou une file d’attente d’appels. Sélectionnez le compte de ressource associé à la destination.
- **Numéro de téléphone externe :** n’importe quel numéro de téléphone. (Voir [les détails techniques du transfert externe).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Messagerie vocale** : boîte vocale associée à Microsoft 365 groupe de messagerie que vous spécifiez. Vous pouvez choisir si vous voulez des transcriptions de messages vocaux et le message « Veuillez laisser un message après le ton ». invite système.
- **Opérateur** (moyen automatique uniquement) - Opérateur défini pour le attendant automatique. La définition d’un opérateur est facultative. Un opérateur peut être l’une des autres destinations de cette liste.

Les attendants automatiques proposent des options de routage d’appel distinctes pour les appels reçus en dehors des heures d’ouverture et des jours fériés. Le routage des appels hors heures d’ouverture autorise toutes les options répertoriées ci-dessus, tandis que le routage des appels en de congés ne permet que de rediriger ou de déconnecter un appel, mais aucune option de touche de numérotation.

Les files d’attente placent l’appelant en attente jusqu’à ce qu’un agent affecté à la file d’attente soit disponible pour prendre son appel. Dans deux situations, un appelant peut être dirigé hors de la file d’attente :

- **Dépassement d’appel** : si le nombre d’appels dans la file d’attente dépasse la limite définie, les nouveaux appelants sont redirigés hors de la file d’attente.
- **Délai d’attente** des appels : si un appelant est dans la file d’attente plus longtemps que le paramètre de délai d’attente configuré, il est redirigé hors de la file d’attente.

Les appels redirigés hors d’une file d’attente peuvent être envoyés vers les destinations de routage des appels répertoriées ci-dessus à l’exception d’un opérateur. (Les files d’attente d’appels n’ont pas d’opérateurs, mais vous pouvez rediriger les appelants vers la même destination qu’un opérateur que vous avez configuré pour un port automatique.)

L’exemple ci-dessous montre un exemple de routage des appels à l’aide de files d’attente et de files d’attente d’appels automatiques.

![Diagramme du routage des appels à l’aide de attendants automatiques et de files d’attente d’appels.](media/attendant-and-queue-call-routing.png)

Dans l’exemple ci-dessus :

- La touche zéro (0) redirige les appelants vers un opérateur. L’opérateur de ce attendant automatique a été configuré en tant que **personne dans l’organisation.**
- La touche 1 redirige les appelants vers la file d’attente d’appels des ventes. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe commerciale affectée à la file d’attente.
- Les deux (2) touches redirigent les appelants vers la file d’attente d’appels du support. Cette file d’attente d’appels est connectée à une équipe qui contient l’équipe de support attribuée à l’équipe.
- La file d’attente d’appels du support dispose d’un numéro de téléphone direct via un attendant automatique intermédiaires. Le fait de laisser un attendant automatique répondre à la ligne de support permet de séparer les heures d’ouverture et le routage des appels en cas de congés.
- La clé trois (3) redirige les utilisateurs vers un autre attendant automatique pour l’annuaire de l’entreprise. Le attendant automatique de l’annuaire de l’entreprise permet aux appelants d’appeler des personnes de l’organisation en composant leur nom ou leur numéro de poste.

Nous vous recommandons de créer un ou plusieurs diagrammes similaires à celui ci-dessus pour macher votre routage des appels. N’oubliez pas d’inclure ce qui suit dans votre diagramme ou dans la documentation :

- Quels sont les attendant automatiques qui auront un accès direct via des numéros de téléphone ?
- Quelles sont les conditions requises pour les heures d’congés et le routage des jours fériés pour chaque employé du service automatique ?
- L’appartenance à chaque file d’attente d’appels. (Vous pouvez ajouter des utilisateurs individuellement ou ma carte de la file d’attente à différents types de groupes. Le mappage d’une file d’attente à une équipe offre une expérience plus polyvalente.)

Voici quelques pratiques meilleures pour le routage des appels :

- Examiner votre système d’appels existant et analyser les types et la fréquence des appels entrants. Utilisez ces informations pour informer votre service de service automatique et la structure des files d’attente d’appels.
- Placez les options les plus courantes en premier dans le menu pour router les appels le plus rapidement possible.
- Évitez de connecter les numéros de service directement aux files d’attente d’appels, sauf si elles sont disponibles 24/24, 7/7. Les files d’attente d’appels n’autorisent pas la gestion distincte des appels pendant les heures d’ouverture ou les jours fériés. Si vous voulez avoir une file d’attente avec un numéro direct, affectez le numéro à un employé de service automatique qui redirige automatiquement vers la file d’attente pendant les heures d’ouverture.
- Si vous recevez de nombreux appels vous demandant des informations de base sur votre entreprise, telles que les heures d’ouverture, l’emplacement ou l’adresse du site web, envisagez de créer un portail automatique pour répondre à ces questions à l’aide de messages enregistrés.
- Conservez la liste des éléments de menu sur au moins cinq éléments. Les appelants peuvent avoir des difficultés à mémoriser plus de cinq options. Utilisez des attendants automatiques imbrmbrés si d’autres options sont nécessaires pour router correctement un appel.
- Décrivez tout d’abord le service, puis l’option d’appuyer (p. ex : Pour les ventes, appuyez sur 1) plutôt que l’inverse (p. ex. Appuyez sur 1 pour appuyer sur Ventes).
- La terminologie utilisateur que vos appelants comprendront plutôt que ce que vous pouvez utiliser en interne.
- Éviter les mises à jour fréquentes du routage des appels. Si vous modifiez à l’avenir les options de menu d’un employé de façon automatique, appelez-le dans les invites vocales pendant les 30 premiers jours.

## <a name="getting-started"></a>Prise en main

Une fois que vous avez terminé les tâches de planification de cet article, suivez ces étapes pour configurer vos files d’attente et les files d’attente automatiques :

1. Obtenez les numéros de service dont vous avez besoin pour les travailleurs automatiques et les files d’attente d’appels que vous voulez rendre accessibles en appelant directement depuis l’extérieur de votre organisation. Cela peut inclure [le transfert de numéros d’un autre fournisseur](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou la demande de nouveaux numéros de [service.](getting-service-phone-numbers.md)

2. Obtenez une [Teams Téléphone - Licence Utilisateur virtuel](teams-add-on-licensing/virtual-user.md) pour chaque compte de ressource que vous prévoyez de créer. Ces licences sont gratuites. Nous vous suggérons donc d’en obtenir quelques supplémentaires si vous décidez de modifier vos comptes de ressources à l’avenir.

3. [Créez un compte de ressource pour](manage-resource-accounts.md) chaque employé automatique et chaque file d’attente d’appels que vous souhaitez créer. Attribuez à chaque compte une Teams Téléphone - Licence Utilisateur virtuel et éventuellement un numéro de service.

4. [Créez les jours](set-up-holidays-in-teams.md) fériés pour lesquels vous souhaitez associer un routage d’appel distinct dans vos attendants automatiques.

5. Vous pouvez également configurer le parc [d’appels](call-park-and-retrieve.md) et la récupération si vous souhaitez utiliser cette fonctionnalité pour faciliter les transferts d’appel.

6. Créez les groupes que vous voulez utiliser pour contenir les agents d’appel pour les files d’attente d’appels.

7. Si vous envisagez d’autoriser la numérotation par poste, assurez-vous d’ajouter le numéro de poste de vos utilisateurs à Azure Active Directory profil.

Une fois que vous avez suivi la procédure ci-dessus, vous êtes prêt à créer vos files d’attente d’appels et de automatiques. Étant donné que les files d’attente automatiques et les files d’attente d’appels peuvent rediriger des appels vers l’un l’autre, consultez le diagramme de flux de travail que vous avez créé pour déterminer le attendant automatique ou la file d’attente d’appels qui doivent être créés en premier. Dans l’exemple dans le diagramme ci-dessus, vous devez créer les files d’attente des ventes et du support avant de créer le attendant automatique principal de Contoso, car celui-ci doit diriger les appelants vers les files d’attente des ventes et du support.

Consultez les articles suivants pour plus d’informations sur la création de attendants automatiques et de files d’attente d’appels :

- [Configurer un attendant automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md)

Si vous avez besoin de fonctionnalités plus étendues, telles que l’intégration aux flux de travail, bots et SMS, envisagez [Azure Communication Services.](/azure/communication-services/overview)

## <a name="related-topics"></a>Sujets associés

[Planifier le routage direct](direct-routing-plan.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Créer une file d’attente d’appels - Didacticiel pour les petites entreprises](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurer un attendant automatique - Didacticiel pour les petites entreprises](business-voice/create-a-phone-system-auto-attendant-smb.md)
