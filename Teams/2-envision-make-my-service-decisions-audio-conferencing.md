---
title: Prendre des décisions pour le service d’audioconférence - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Apprenez-en davantage sur les réunions, les licences et la disponibilité, la configuration des paramètres du pont de conférence, l’acquisition ou le transfert de numéros de téléphone, et le choix de plans de numérotation client.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0155788ef4ba99a350be0043847edd5e705b75b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240574"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de service

Pour planifier l’implémentation technique de l’audioconférence, vous devez prendre des décisions de service à plusieurs avances pour mieux préparer votre organisation à mettre en place une solution qui répond à vos besoins professionnels définis.

## <a name="audio-conferencing-in-teams"></a>Audioconférence dans teams

Dans le cadre de la définition des fonctionnalités d’audioconférence requises dans Microsoft Teams, l’une des premières étapes consiste à évaluer la dernière introduction publique pour déterminer:

-   Fonctionnalités de l’audioconférence dans les équipes qui seront déployées pour les utilisateurs de l’étendue.

-   Conditions requises pour les fonctionnalités utilisateur pour l’audioconférence dans Teams.

-   Dans la barre de planning de votre déploiement, vous avez besoin de confirmer que les fonctionnalités de l’audioconférence dans les équipes décrites dans la dernière barre d’évolution publique répondent à vos besoins en matière d’utilisation, de fonctionnalités et d’étendue.

> [!NOTE]
> Le plan de la dernière version des équipes permettant d’identifier les fonctionnalités de l’audioconférence teams dans <https://aka.ms/O365Roadmap>l’objectif de votre déploiement est disponible à l’adresse.

## <a name="meetings-in-teams"></a>Réunions dans Teams

Teams permet à vos utilisateurs de planifier et de participer à des réunions en ligne à l’aide des options de la vidéo HD, de la voix sur IP (VoIP) et des options de conférence rendez-vous RTC.

Les réunions peuvent être planifiées en tant que réunions privées (seules les parties invitées peuvent être jointes) ou à des réunions de canal (ouvertes pour tous les utilisateurs ayant accès au canal) et vos utilisateurs peuvent également démarrer des réunions impromptues au sein des canaux.

> [!NOTE]
> Pour en savoir plus sur les fonctionnalités des réunions dans Microsoft Teams, reportez-vous à la [documentation Microsoft 365](https://aka.ms/O365Roadmap).

Les participants à la réunion peuvent rejoindre les réunions de votre équipe en vous connectant aux numéros de téléphone de conférence rendez-vous gratuits ou payants par téléphone fixe ou mobile. De plus, les utilisateurs peuvent laisser le service d’audioconférence lancer la fonctionnalité «m’appeler» pour pouvoir participer à une réunion en faisant en sorte que le pont de conférence appelle leurs téléphones (utile lorsque la connexion de données n’est pas fiable), ou permet aux organisateurs de la réunion d’inviter une réunion. participants en composant un numéro de téléphone.

> [!IMPORTANT]
> L’audioconférence dans Teams ne prend pas en charge les fournisseurs de services d’audioconférence tiers (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilité de l’audioconférence

Avant de planifier l’implémentation de l’audioconférence dans Teams, vous devez examiner la disponibilité du service de visioconférence comme décrit dans disponibilité du [pays et de la région pour les offres de conférence et d’appels audio](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison de contraintes juridiques, pour que les services d’audioconférence puissent être mis à la disposition des organisations multinationales, le contrat pour les abonnements Office 365 doit être source de pays et de régions dans lesquels le service de conférence audio est disponible au bureau.

Après confirmation de votre organisation, il est possible d’obtenir le service de conférence audio, de la liste des emplacements des utilisateurs ou des bureaux dans lesquels vous implémenterez le service d’audioconférence, en fonction de la liste des pays et régions disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements des utilisateurs ou les bureaux qui implémenteront le service de conférence audio.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements ou les bureaux des utilisateurs à activer pour le service de conférence audio.</li></ul>|

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de liste d’activation de site de conférence audio:
> 
> |Bureau   |Emplacement |Service de conférence PSTN  |
> |---------|---------|---------|
> |1 Eppîng Road|Australie|Audioconférence,|
> |100 Cyberport Road|Hong Kong R.A.S.|Conférence PSTN héritée|
> |1 Marina Boulevard|Singapour|Audioconférence,|
> |32 London Bridge Street|Royaume-Uni|Audioconférence,|
> |39 quai du Président Roosevelt|France|Audioconférence|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licences pour l’audioconférence

Une [licence d’audioconférence](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) est disponible dans le cadre des offres d’abonnement Office 365 E5 ou en tant que service d’extension pour les offres d’abonnement Office 365 E1 ou Office 365 E3.

> [!NOTE]
> La Conférence RTC ou rendez-vous dans Teams ne prend pas en charge les fournisseurs de services d’audioconférence tiers (ACPs).
> <br>Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.

Pour fournir des numéros de téléphone de conférence rendez-vous gratuits et prendre en charge les appels vers des numéros internationaux, vous devez configurer des [crédits de communication](what-are-communications-credits.md) pour votre organisation.

> [!IMPORTANT]
> Certains pays sont pris en service par des numéros de téléphone gratuits de conférence sans frais. Pour prendre en charge les appels entrants dans ces pays, vous devez utiliser des crédits de communication.

La première considération lors de l’implémentation de crédits de communications consiste à choisir le montant initial des fonds que vous voulez acheter. Si votre organisation choisit d’utiliser la recharge automatique, vous devez décider du montant du déclenchement (le plus petit montant possible) et du montant de la recharge automatique. Votre utilisation réelle détermine le montant de la recharge automatique. Nous vous conseillons de surveiller l’utilisation des crédits de communication au fil du temps et de régler le montant de la recharge si nécessaire.

Vous pouvez en savoir plus sur les crédits de communication [ici](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation n’a pas déjà acheté le programme de licence d’audioconférence requis, déterminez si vous allez acquérir des licences de conférence audio en intensifsant les abonnements Office 365 existants ou en acquérant des licences de complément de conférence audio.</li><li>Déterminez si les crédits de communication sont requis pour l’implémentation de votre audioconférence. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les utilisateurs auxquels des licences de conférence audio seront attribuées.</li><li>Documentez le plan de communication crédits (montant initial, montant du déclenchement, montant de la recharge automatique).</li></ul>|

> [!TIP]
> Vous pouvez documenter la liste d’attribution de licence pour les utilisateurs de l’audioconférence en utilisant l’exemple suivant.
> 
> |Utilisateur  |Bureau  |Licence Office 365  |
> |---------|---------|---------|
> |Adele Vance|1 Eppîng Road|Office 365 E5|
> |Alex Wilber|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
> |Ben Walters|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
> |Christie Cline|1 Marina Boulevard|Office 365 E3, complément pour l’audioconférence|
> |Debra Berger|1 Marina Boulevard|Office 365 E5|
> |Lee Gu|1 Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Louis Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|

<br>

> [!TIP]
> Vous pouvez documenter les numéros de planification de vos crédits de communication comme suit :
>
> |         |         |
> |---------|---------|
> |Montant initial|1 000 $|
> |Montant déclencheur|400 $|
> |Montant de la recharge automatique|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Numéros de pont de téléconférence

Le service d’audioconférence dans Office 365 inclut les éléments suivants :

-   Plusieurs types de numéros de téléphone de pont de conférence (payant et gratuit)

-   Plusieurs catégories de numéros de téléphone de pont de conférence (dédié et partagé)

-   prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;

-   Un numéro de téléphone par défaut pour le client

> [!NOTE]
> Les numéros de téléphone du pont de conférence dédié comptent en fonction du nombre de numéros de téléphone qui peuvent être acquis par locataire en fonction du nombre de licences applicables. Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.

Si vous devez transférer des numéros de téléphone de pont de conférence existants vers le service d’audioconférence, en supposant qu’ils répondent à des exigences spécifiques au pays, vous pouvez transférer ces numéros de téléphone de pont de conférence vers Microsoft.

> [!NOTE]
> La complexité du transfert des numéros de téléphone vers Microsoft varie considérablement selon le pays ou la région, l’opérateur, le nombre de circuits concernés et de nombreux autres facteurs contributeurs. Travaillez avec votre fournisseur actuel pour déterminer le temps nécessaire pour vous assurer que le processus de démarrage du processus doit être assez rapide pour répondre à vos plannings.

Pour en savoir plus sur les numéros de téléphone de la Conférence, consultez les articles suivants:

-   [Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Numéros de téléphone pour l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtention de numéros de téléphone de service](getting-service-phone-numbers.md)

-   [Transférer les numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation a besoin des numéros de téléphone de pont de conférence spécifiques.</li><li>Déterminez la manière dont les numéros de téléphone du pont de conférence dédiés seront obtenus pour les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation de l’audioconférence (qui obtient de Microsoft ou de transférer des numéros de téléphone existants).</li><li>Si vous décidez de les obtenir de la part de Microsoft, déterminez la méthode à utiliser (soumission de formulaire ou automatique) pour les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation de l’audioconférence.</li><li>Déterminez les préférences linguistiques à configurer pour chaque numéro de téléphone de pont de conférence dédié.</li><li>Déterminez le numéro de téléphone du pont de conférence par défaut du client.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez le plan principal de l’acquisition d’un numéro de téléphone, en détaillant la façon dont les numéros de téléphone seront obtenus pour chaque emplacement ou bureau dans le cadre de l’implémentation de l’audioconférence.</li><li>Le cas échéant, remplissez le formulaire de demande de nouveau numéro de téléphone (un formulaire pour chaque emplacement ou bureau).</li><li>Documentez les configurations détaillées des numéros de téléphone de votre pont de conférence (numéros de téléphone de conférence partagés et dédiés, préférences linguistiques pour chaque numéro de téléphone de pont de conférence par défaut).</li></ul>|

Vous trouverez ci-dessous un exemple de modèle que vous pouvez utiliser pour capturer les détails de votre pont de conférence.

> [!TIP]
> Voici un exemple de modèle pour capturer les détails du pont de téléconférence :
> 
> |Bureau   |Acquisition de numéro de pont de téléconférence et type de pont |Numéro du pont  |Langue du pont|
> |---------|---------|---------|---------|
> |1 Eppîng Road|Acquisition d'un nouveau numéro de pont dédié|TBA|Anglais (Australie)|
> |1 Marina Boulevard|Acquisition d'un nouveau numéro de pont partagé|TBA|Anglais (États-Unis), Chinois (simplifié, RPC)|
> |32 London Bridge Street|Port existant, dédié|+44 20 7946 0001|Anglais (Royaume-Uni)|
> |39 quai du Président Roosevelt|Acquisition d'un nouveau numéro de pont dédié|TBA|Français (France), Anglais (Royaume-Uni)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Paramètres du pont de téléconférence

Pour personnaliser davantage l’utilisation de l’utilisateur, vous pouvez configurer les options à l’échelle de l’Organisation pour la participation à des réunions d’audioconférence (entrée de réunion et de sortie et enregistrement de nom d’appelant), la longueur du code confidentiel de l’organisateur de la réunion et les notifications par courrier électronique:

-   Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.

-   La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.

-   Les courriers électroniques de notification envoyés lors de l’activation de la licence d’audioconférence ou de toute autre modification gérée par l’administrateur sont activés par défaut. Vous pouvez désactiver cette fonctionnalité et prendre le contrôle des communications utilisateur de votre organisation.

Pour les utilisateurs auxquels une licence de conférence audio est affectée, les numéros payants ou gratuits par défaut indiqués dans les coordonnées de l’audioconférence peuvent être configurés de manière à utiliser:

-   Par défaut au niveau du client.

-   Les numéros de téléphone du pont de conférence automatiquement attribués.

-   Des numéros de téléphone de pont de conférence configurés manuellement pour chaque utilisateur.

Les numéros de téléphone de pont de conférence spécifiques à l’utilisateur sont généralement utiles dans les organisations globales ou nationales et doivent fournir des numéros locaux comme numéros de téléphone de pont de conférence par défaut dans leurs invitations aux réunions.

Les participants qui se connectent à partir de différentes villes ou à l’étranger peuvent chercher des numéros supplémentaires configurés au niveau du client, mais ces numéros n’apparaissent pas directement dans les invitations aux réunions. Les invitations aux réunions fournissent un lien vers la page des numéros de connexion de la **Conférence teams** pour qu’ils puissent chercher le numéro de téléphone du pont de conférence le plus proche de leur emplacement.

Vous pouvez également configurer la gestion des appelants non authentifiés par chaque organisateur de la réunion, si vous souhaitez que l’organisateur de la réunion démarre la réunion avant que les appelants non authentifiés puissent être admis ou autorisent les appelants non authentifiés à démarrer une réunion. .

Vous pouvez également appliquer des configurations supplémentaires à chaque utilisateur pour contrôler l’utilisation des numéros de téléphone de conférence rendez-vous gratuits et des appels sortants d’une conférence.

> [!NOTE]
> Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces. Vous pouvez inscrire votre organisation dans le programme preview de https://www.skypepreview.com.

À l’aide de ces commandes, vous pouvez choisir si les organisateurs de la réunion peuvent fournir des numéros de téléphone de conférence rendez-vous gratuits pour les réunions organisées par eux et si les participants peuvent se connecter à partir des réunions qu’ils ont organisées. Le niveau de contrôle de numérotation s’étend de tout blocage de la numérotation, pour autoriser les appels sortants vers des numéros nationaux uniquement, en autorisant la numérotation vers les numéros nationaux et internationaux.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation nécessite des notifications d’entrée et de sortie, et — si tel est le cas, le type de notification à mettre en œuvre (tonalités, numéros de téléphone ou nom enregistré).</li><li>Définissez la longueur du code confidentiel de l’audioconférence qui répond à vos exigences de sécurité de votre organisation.</li><li>Déterminez si votre organisation veut prendre le contrôle des communications des utilisateurs liés au service de conférence audio.</li><li>Déterminez les numéros de téléphone du pont de conférence à attribuer à chaque organisateur de la réunion.</li><li>Déterminez si certaines organisateurs de la réunion doivent utiliser des numéros de téléphone de conférence sans frais pour leurs réunions.</li><li>Déterminez si certains organisateurs de la réunion doivent autoriser les appelants non authentifiés à démarrer une réunion.</li><li>Déterminez si certaines organisateurs de la réunion doivent avoir besoin d’une conférence téléphonique pour être contrôlée.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration)</li><li>Documentez les numéros de téléphone du pont de conférence à attribuer à chaque organisateur de la réunion et le paramètre correspondant pour contrôler la politique des appelants non authentifiés, ainsi que les contrôles de numérotation et de numérotation gratuits.</li></ul>|

> [!TIP]
> Les paramètres de votre pont de conférence peuvent être documentés comme dans l’exemple suivant.
> 
> |         |         |
> |---------|---------|
> |Activer les notifications d’accès et de sortie de réunion|Activé|
> |Type d’annonce d’accès/sortie|Tonalités|
> |Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion|Désactivé|
> |Longueur du code PIN|5|
> |Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de numérotation changent|Désactivé|

<br>

> [!TIP]
> Vous pouvez documenter la liste des affectations des paramètres du pont de conférence pour les utilisateurs de l’audioconférence en utilisant l’exemple suivant.
>
> |Utilisateur  |Bureau  |Numéro payant par défaut  |Numéro gratuit par défaut  |Autoriser le numéro gratuit  |Les appelants non authentifiés contournent la salle d’attente  |Composition de numéros depuis la conférence  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|1 Eppîng Road|TBA|TBA|Oui|Activé|Internationaux et nationaux|
> |Alex Wilber|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
> |Ben Walters|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
> |Christie Cline|1 Marina Boulevard|TBA|TBA|Oui|Désactivé|Nationaux|
> |Debra Berger|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
> |Lee Gu|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Activé|Non autorisé|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
> |Louis Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Oui|Activé|Internationaux et nationaux|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone vocaux Cloud

Pour l’implémentation de l’audioconférence, vous pouvez choisir d’acheter de nouveaux numéros de téléphone ou de transférer/porter des numéros de téléphone existants.

Pour permettre aux utilisateurs de composer les numéros de téléphone tels qu’ils sont habitués (par exemple, en omettant les indicatifs pour les appels locaux), en omettant le code du pays pour les appels nationaux ou même en utilisant la numérotation abrégée lors de la Conférence rendez-vous, vous pouvez configurer un plan de numérotation personnalisé. et attribuez-la à vos utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquisition de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions Microsoft Cloud Voice sont les suivants:

-   Des numéros d’abonnés (utilisateurs), qui peuvent être attribués à des utilisateurs de votre organisation.

-   Les numéros de service, disponibles en tant que numéros de service gratuits ou payants, qui ont une plus grande capacité d’appel simultanée que les numéros d’abonné, peuvent être attribués à des services tels que les conférences audio, les standards automatiques ou les files d’attente d’appels.

Pour plus d’informations sur ces types de numéros de téléphone, reportez-vous à [différents types de numéros de téléphone utilisés pour les offres d’appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Le nombre total de numéros de téléphone que vous pouvez obtenir dépend des types de numéros de téléphone et du nombre de licences que vous avez achetées et attribuées à vos utilisateurs.

Lorsqu’il s’agit des numéros de service, vous devez planifier soigneusement l’implémentation de votre audioconférence. Évaluez si votre entreprise a besoin de numéros de téléphone de conférence de conférence spécifiques. Si ce n’est pas le cas, votre organisation peut choisir d’utiliser les numéros de téléphone de pont de conférence partagés.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, voir [combien de numéros de téléphone pouvez-vous obtenir?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements ou les bureaux des utilisateurs dans lesquels de nouveaux numéros de téléphone seront achetés auprès de Microsoft.</li><li>Choisissez le type de numéro de téléphone à acquérir auprès de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements ou les bureaux des utilisateurs dans lesquels de nouveaux numéros de téléphone seront achetés auprès de Microsoft.</li><li>Documentez le type de numéro de téléphone à acquérir auprès de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transférer des numéros de téléphone existants

Si votre organisation souhaite transférer (ou porter) des numéros de téléphone existants à Microsoft, vous pouvez le faire en envoyant une demande de transfert à Microsoft.

Vous pouvez transférer tous vos numéros de téléphone existants à la fois (port complet) et, dans certains pays, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existants (port partiel). Un port partiel peut s’avérer utile dans les cas où vous souhaitez simplement déplacer le pont de conférence rendez-vous vers le service de conférence rendez-vous.

Une demande de transfert unique peut uniquement transférer les numéros de téléphone vers un même type de numéro de téléphone. Si vous avez besoin de transférer certains de vos numéros de téléphone et d’autres en tant que numéros de service, nous vous recommandons de commencer par le transfert vers Microsoft, puis de procéder à la conversion dès que les numéros sont dans le contrôle de Microsoft.

En guise d’alternative, si le port partiel est pris en charge, vous pouvez demander plusieurs demandes de port, une demande de port à la fois. Toutefois, cette approche peut prolonger votre contrat avec votre fournisseur de services de télécommunication existant.

Le portage des numéros de téléphone est un sujet complexe qui nécessite une planification et une coordination complètes, et la gestion appropriée des attentes des parties prenantes. Pour en savoir plus, consultez les articles suivants:

-   [Transfert de numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Transfert des questions fréquemment posées numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements ou les bureaux des utilisateurs dans lesquels les numéros de téléphone existants seront transférés vers Microsoft.</li><li>Choisissez le type de numéro de téléphone à transférer vers Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements ou les bureaux des utilisateurs dans lesquels les numéros de téléphone existants seront transférés vers Microsoft.</li><li>Documentez le type de numéro de téléphone à transférer vers Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un plan de numérotation dans la fonctionnalité système téléphonique d’Office 365 est un ensemble de règles de normalisation qui convertit les numéros de téléphone numérotés dans un autre format (généralement le format E. 164) pour l’autorisation et le routage des appels. Le service d’audioconférence utilise les mêmes fonctionnalités utilisées par le système téléphonique pour traduire les numéros de téléphone de conférence rendez-vous dans les scénarios de numérotation de conférences (par exemple, invitez des participants via PSTN et Dial-moi).

Dans la fonctionnalité système téléphonique d’Office 365, il existe deux types de plans de numérotation:

-   **Plan de numérotation service:** Il s’agit du plan de numérotation par défaut qui est appliqué aux utilisateurs en fonction de leur emplacement d’utilisation d’Office 365 et ne peut pas être modifié.

-   **Plan de numérotation client:** Il s’agit d’un plan de numérotation personnalisable au sein d’un client, qui est divisée en deux types:

    -   **Client-plan de numérotation global:** Plan de numérotation qui s’applique à tous les utilisateurs du client.

    -   **Plan de numérotation de l’utilisateur:** Plan de numérotation s’appliquant uniquement à des utilisateurs spécifiques.

Le plan de numérotation efficace attribué aux utilisateurs est la combinaison du plan de numérotation service (basé sur l’emplacement d’utilisation d’Office 365 d’un utilisateur) et du plan de numérotation client.

Le ![tableau suivant présente trois combinaisons de plans de services et de numérotation client.] Le (media/audio_conferencing_image8.png "tableau suivant présente trois combinaisons de plans de services et de numérotation client.")

> [!Important]
> Chaque plan de numérotation client peut comporter un maximum de 25 règles de normalisation. par conséquent, il est important de ne pas dupliquer les règles de normalisation déjà disponibles dans le cadre du plan de numérotation service.

Pour en savoir plus sur les plans de numérotation, reportez-vous à la rubrique [Présentation des plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation nécessite des plans de numérotation personnalisés (exigences d’entreprise, exigences d’adoption, etc.).</li><li>Le cas échéant, déterminez l’étendue du plan de numérotation client (client-global ou utilisateur client) pour prendre en charge les exigences relatives aux plans de numérotation personnalisés.</li><li>Le cas échéant, déterminez les plans de numérotation client que vous allez créer pour prendre en charge les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation de la voix Cloud.</li><li>Le cas échéant, Déterminez quels utilisateurs nécessitent un plan de numérotation personnalisé et le plan de numérotation client à attribuer pour chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de votre implémentation de voix Cloud.</li><li>Documentez les utilisateurs auxquels vous voulez attribuer un plan de numérotation personnalisé et le plan de numérotation client à attribuer à chaque utilisateur.</li></ul>|

> [!TIP]
> S’il est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations du plan de numérotation client.
> 
> |Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^ (7-d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000-€ € "x8999) pour OMB Office, Singapour_|^ (8{3}<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^ (1? 800 p{7}) \d * $<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000-€ € "x7999) pour 39 quai du Président Roosevelt Office, Issy-aux-Moulineaux, France_|^ (7-d{3}) $<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0? (80 \n d{7}) \d * $<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1-d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>
> |Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
> |---------|---------|---------|---------|
> |Adele Vance|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Alex Wilber|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Ben Walters|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Christie Cline|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Debra Berger|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Lee Gu|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Louis Lahr|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions relatives au service de documents 

Utilisez les informations des sections précédentes de cet article pour documenter les décisions de votre service. En règle générale, cette documentation contient les sections principales suivantes:

-   Liste d’habilitations de sites pour le service d’audioconférence

-   Liste d’attributions de licences pour les organisateurs de réunions en audioconférence

-   Numéros de planification de crédits de communication

-   Détails du pont de téléconférence

-   Paramètres du pont de téléconférence

-   Affectations de paramètres de pont de téléconférence

-   Forfaits d’acquisition des numéros de téléphone

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->