---
title: Prendre des décisions pour le service d’audioconférence - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 12/28/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: En savoir plus sur les réunions, gestion des licences et la disponibilité, configurer les paramètres de pont de conférence, acquérir ou transférer des numéros de téléphone, choisissez client plans de numérotation.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0057f18d334c89f745ec74952fd01796c8b30880
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458501"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de mon service

Pour planifier l’implémentation technique de conférence Audio, vous devez apporter une série de décisions de service à l’avance pour mieux préparer votre organisation pour implémenter une solution qui répond aux besoins de votre entreprise défini.

## <a name="audio-conferencing-in-teams"></a>Services d’audioconférence dans les équipes

Dans le cadre de la définition des fonctionnalités de conférence Audio requises dans Microsoft Teams, une des premières étapes consiste à évaluer la feuille de route public le plus récent pour déterminer :

-   Les fonctionnalités de conférence Audio dans les équipes qui seront déployés pour les utilisateurs dans l’étendue.

-   Prévu des besoins des utilisateurs des fonctionnalités de conférence Audio dans les équipes.

-   Confirmation que les fonctionnalités de conférence Audio dans les équipes décrits dans la feuille de route public le plus récent répondent à vos utilisateurs, les fonctionnalités et exigences d’étendue, dans la chronologie de votre déploiement.

> [!NOTE]
> La feuille de route équipes le plus récent pour identifier les fonctionnalités d’audioconférence équipes dans l’étendue de votre déploiement se trouvent à <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Réunions dans Teams

Équipes permet à vos utilisateurs à planifier et participer à des réunions en ligne à l’aide de vidéo haute définition, voix sur IP (VoIP) et RTC options conférence rendez-vous.

Réunions peuvent être programmées en tant que les réunions privées (seules les parties invités peuvent rejoindre) ou canal réunions (ouvert pour tous les utilisateurs ayant accès à la chaîne) et vos utilisateurs peuvent également démarrer des réunions virtuelles impromptues canaux.

> [!NOTE]
> Pour plus d’informations sur les fonctionnalités de réunions dans les équipes, voir [Skype pour les entreprises à des fonctions de feuille de route les équipes Microsoft] https://aka.ms/skype2teamsroadmap).

Participants à la réunion peut participer à vos réunions d’équipes en appelant le numéro payant ou le pont de conférence rendez-vous gratuit par le biais des réseaux terrestres ou des téléphones mobiles, les numéros de téléphone. En outre, les utilisateurs peuvent laisser le service de conférence Audio initier la fonctionnalité « m’appeler » afin qu’ils peuvent participer à une réunion en ayant le pont de conférence appeler leurs téléphones (utile lors de la connexion de données n’est pas fiable), ou une réunion permettent aux organisateurs inviter de réunion participants à la connexion à leurs téléphones.

> [!IMPORTANT]
> Services d’audioconférence dans les équipes ne prend en charge des fournisseurs de services d’audioconférence tiers (ACP).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilité de l’audioconférence

Avant de planifier l’implémentation de conférence dans les équipes, vous devez consulter la disponibilité du service de conférence Audio comme indiqué dans le [pays et région disponibilité pour la conférence Audio et des Plans de l’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison des contraintes juridiques, pour une audioconférence soient disponibles pour les organisations multinationales, le contrat pour les abonnements Office 365 doit provenir de pays et régions où le service de conférence Audio est disponible sur le marché.

Après avoir confirmé que votre organisation est éligible pour obtenir le service de conférence Audio, compiler la liste des emplacements de l’utilisateur ou de bureaux où vous allez implémenter le service de conférence Audio, en fonction de la liste des pays et régions disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements des utilisateurs ou les bureaux qui implémenteront le service d’audioconférence.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consignez les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service d’audioconférence.</li></ul>|

> [!TIP]
> Voici un exemple d’un modèle de liste de conférence Audio site activation :
> 
> |Bureau   |Emplacement |Service de conférence PSTN  |
> |---------|---------|---------|
> |1 Eppîng Road|Australie|Audioconférence|
> |100 Cyberport Road|Hong Kong R.A.S.|Conférence PSTN héritée|
> |1 Marina Boulevard|Singapour|Audioconférence|
> |32 London Bridge Street|Royaume-Uni|Audioconférence|
> |39 quai du Président Roosevelt|France|Audioconférence|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licences pour l’audioconférence

Une [licence de conférence Audio](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) est disponible dans le cadre des plans d’abonnement Office 365 E5, ou en tant que module complémentaire de service pour les plans d’abonnement à Office 365 E1 ou Office 365 E3.

> [!NOTE]
> Conférence PSTN ou un rendez-vous dans les équipes ne prend en charge des fournisseurs de services d’audioconférence tiers (ACP).
> <br>Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.

Pour fournir des numéros de téléphone de pont de conférence gratuit et pour prendre en charge la conférence rendez-vous aux numéros de téléphone international, vous devez configurer [Les crédits de Communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) pour votre organisation.

> [!IMPORTANT]
> Certains pays sont traitées par les numéros de téléphone des pont de conférence gratuit uniquement. Pour prendre en charge la numérotation dans ces pays, vous devez utiliser Communications générique.

Le premier point important lors de l’implémentation des Communications crédits est à décider de la quantité initiale de fonds que vous souhaitez acheter. Si votre organisation décide d’utiliser recharge automatique, vous devez décider le déclencheur montant (la plus faible des fonds) et la quantité recharge automatique. Votre utilisation réelle déterminera le montant auto-recharge. Vous devez surveiller l’utilisation de Communications crédits au fil du temps et ajuster le montant recharge selon les besoins.

Vous en apprendrez plus sur les Communications crédits [ici](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation n’a pas déjà acheté la gestion des licences de conférence Audio requis, décidez si vous allez vous procurer des licences de conférence Audio en activant des abonnements Office 365 existants ou à acquérir des licences de module complémentaire de conférence Audio.</li><li>Déterminer si les Communications crédits requis pour votre implémentation de conférence Audio. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les utilisateurs affectés des licences de conférence Audio du document.</li><li>Documenter le plan de communication crédits (quantité initiale, quantité déclencheur, quantité recharge automatique)</li></ul>|

> [!TIP]
> Vous pouvez documenter la liste d’affectation de licence pour les utilisateurs de conférence Audio à l’aide de l’exemple suivant.
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

-   Plusieurs types de conférence combler les numéros de téléphone (payant et gratuit)

-   Plusieurs catégories de pont de conférence de numéros (partagé et dédié)

-   prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;

-   Un numéro de téléphone par défaut pour le client

> [!NOTE]
> Dédié pont téléphone numéros nombre de conférences la limite des numéros de téléphone qui peuvent être acquise par client, en fonction du nombre de licences. Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.

Si vous devez transférer existant numéros de téléphone de pont de conférence pour le service de conférence Audio, en supposant qu’ils répondent aux exigences spécifiques à un pays, vous pouvez transférer ces numéros de téléphone du pont conférence existante à Microsoft.

> [!NOTE]
> La complexité de transfert des numéros de téléphone à Microsoft varie considérablement en fonction du pays ou région, opérateur, nombre de circuits impliqués et plusieurs autres facteurs. Travailler avec votre fournisseur d’étudier la question combien il s’agit comptez pour vous assurer que vous démarrez le processus tôt suffisant pour répondre à vos chronologies.

Pour en savoir plus sur les numéros de téléphone de pont de conférence, consultez les articles suivants :

-   [Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Numéros de téléphone pour l'audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtenir des numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Transférer des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation a besoin de numéros de téléphone de pont de conférence dédiée.</li><li>Décidez comment les numéros de téléphone de pont de conférence dédiée seront obtenus de bureaux ou emplacements de l’utilisateur dans la portée de l’implémentation de conférence Audio (qui est, obtenir à partir de Microsoft ou transfert de numéros de téléphone existants).</li><li>Si vous choisissez d’obtenir auprès de Microsoft, choisissez la méthode à utiliser (l’envoi du formulaire ou automatique) pour les emplacements de l’utilisateur ou de bureaux dans la portée pour l’implémentation de conférence Audio.</li><li>Choisir les préférences linguistiques à configurer pour chaque numéro de téléphone de pont de conférence dédiée.</li><li>Déterminer le numéro de téléphone de pont de conférence client par défaut.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter la planification de l’acquisition de numéro de téléphone, détaillant comment les numéros de téléphone seront obtenus pour chaque utilisateur ou office dans la portée de l’implémentation de conférence Audio.</li><li>Le cas échéant, remplissez le formulaire nouvelle demande de numéro de téléphone, un formulaire pour chaque emplacement ou le bureau.</li><li>Document le pont de conférence détaillées de téléphone numéros configurations (shared et dédiée des numéros de téléphone de pont de conférence, préférences de langue pour chaque numéro de téléphone de conférence dédiée pont, numéro de téléphone de client par défaut conférence pont).</li></ul>|

Voici un exemple d’un modèle que vous pouvez utiliser pour capturer les détails de pont de conférence.

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

Pour personnaliser davantage l’expérience utilisateur, vous pouvez configurer les options d’échelle de l’organisation pour participer à des réunions de conférence Audio (entrée et sortie notification et appelant nom d’enregistrement de la réunion), l’organisateur de la réunion longueur du code confidentiel et notification par courrier électronique :

-   Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.

-   La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.

-   Notification de courriers électroniques envoyés sur l’activation de la licence d’audioconférence ou toute autre modification piloté par l’administrateur sont activées par défaut. Vous pouvez désactiver cette fonctionnalité et prendre le contrôle des communications des utilisateurs de votre organisation.

Pour les utilisateurs qui ont une licence de conférence Audio, les numéros par défaut payant/toll-free, indiqués dans les coordonnées de conférence Audio, peuvent être configurés pour utiliser :

-   La valeur par défaut au niveau du client.

-   Les numéros de téléphone de pont de conférence affecté automatiquement.

-   Un pont numéros conférence configuré manuellement pour chaque utilisateur.

Conférence spécifique à l’utilisateur un pont téléphone numéros sont généralement utiles dans les organisations national ou globales où les utilisateurs sont distribués et doivent fournir des numéros locaux en tant que les numéros de téléphone de pont de conférence par défaut dans les invitations aux réunions.

Les participants se joindre à partir de différentes villes ou étranger peuvent de rechercher des numéros supplémentaires configurés au niveau du client, mais ces chiffres n’apparaissent pas directement dans les invitations aux réunions. Les invitations aux réunions fournissent un lien qui mène des participants à la page de **numéros de téléphone conférence équipes** pour pouvoir rechercher le numéro de téléphone conférence pont le plus proche de leur emplacement.

Vous pouvez également configurer les appelants comment non authentifiés sont gérés par chaque organisateur individuels — s’il convient d’exiger l’organisateur de la réunion pour démarrer la réunion avant les appelants non authentifiés peuvent être admis ou autoriser non authentifié appelants pour démarrer une réunion .

Vous pouvez également appliquer des configurations supplémentaires pour chaque utilisateur de contrôler l’utilisation des numéros de téléphone de pont de conférence gratuit entrants et sortants à partir d’une conférence.

> [!NOTE]
> Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces. Vous pouvez inscrire votre organisation dans le programme Aperçu à partir de https://www.skypepreview.com.

Avec ces contrôles, vous pouvez décider si les organisateurs de réunion peuvent fournir des numéros de téléphone de pont de conférence gratuit pour les réunions organisées par les, et si les participants puissent se connecter à des réunions qu’ils organisés. Le niveau de contrôle d’appel sortant s’étend sur empêchent complètement les appels sortants, pour autoriser uniquement les appels sortants aux numéros nationaux, pour autoriser les appels sortants aux numéros nationales et internationales.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si votre organisation requiert des notifications d’entrée et de sortie, et — dans ce cas, le type de notification à mettre en œuvre (tonalités, numéro de téléphone ou nom enregistré).</li><li>Décidez de la longueur de code confidentiel de conférence Audio qui répond à vos besoins de sécurité de l’organisation.</li><li>Déterminez si votre organisation souhaite prendre le contrôle des communications utilisateur liées au service de conférence Audio.</li><li>Déterminez les numéros de pont de téléconférence à attribuer à chaque organisateur de réunions.</li><li>Décider si certains organisateurs de réunion doivent utiliser des numéros de téléphone de pont de conférence gratuit pour leurs réunions.</li><li>Décider si certains organisateurs de réunion doivent autoriser les appelants non authentifiés à démarrer une réunion.</li><li>Décider si certains organisateurs de réunion doivent conférence rendez-vous soit contrôlé.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration)</li><li>Les numéros de téléphone de pont de conférence pour être affectée à chaque organisateur de la réunion et le paramètre correspondant pour contrôler la stratégie pour les appelants non authentifiés et gratuit de documents et des contrôles de numérotation.</li></ul>|

> [!TIP]
> Vos paramètres de pont de conférence peuvent être documentés comme dans l’exemple suivant.
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
> Vous pouvez documenter la liste d’affectation de paramètres de conférence pont pour les utilisateurs de conférence Audio à l’aide de l’exemple suivant.
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

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone de voix dans le nuage

Pour l’implémentation de conférence Audio, vous pouvez choisir d’acquérir de nouveaux numéros de téléphone/port de transfert de numéros de téléphone existants.

Pour permettre aux utilisateurs de composer des numéros de téléphone de la façon dont ils êtes habitués à — comme omettant indicatifs pour les appels locaux, en omettant le code du pays pour les appels nationaux ou même à l’aide de courte chiffre lors de la conférence de numérotation des appels sortants, vous pouvez configurer un plan de numérotation personnalisé et attribuer aux utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquérir de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions de voix dans le cloud Microsoft sont les suivants :

-   Numéros d’abonné (utilisateur), qui peuvent être affectés aux utilisateurs de votre organisation.

-   Numéros de service, disponibles en tant que numéro payant et numéros gratuits service, qui ont la capacité d’appels simultanés plus élevée que les numéros d’abonné et peuvent être affectés aux services tels que la conférence Audio, les standards automatiques ou files d’attente des appels.

Pour plus d’informations sur ces types de numéros de téléphone, voir [différents types de numéros de téléphone utilisés pour les Plans de l’appel](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Le nombre total de téléphone que vous pouvez obtenir les numéros varient selon les types de numéros de téléphone et le nombre de licences que vous avez acheté et affecté à vos utilisateurs.

Lorsqu’il s’agit du numéro de service, vous devez planifier avec soin votre implémentation de conférence Audio. Déterminer si votre entreprise a besoin de numéros de téléphone du pont de conférence dédiée ; Si ce n’est pas le cas, votre organisation peut choisir d’utiliser des numéros de téléphone de pont de conférence partagé.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, voir [combien de numéros de téléphone peut obtenir ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements de l’utilisateur ou les bureaux où nouveaux numéros de téléphone seront acquis à partir de Microsoft.</li><li>Choisir le type de numéros de téléphone à acquérir de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où nouveaux numéros de téléphone seront acquis à partir de Microsoft.</li><li>Le type de numéros de téléphone à acquérir de Microsoft du document.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfert des numéros de téléphone existants

Si votre organisation souhaite transférer (ou le port) existante de numéros de téléphone à Microsoft, vous pouvez le faire en envoyant une demande de commande de port à Microsoft.

Vous pouvez transférer tous les vos numéros de téléphone existants à la fois (port complète), et, dans certains marchés, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existant (port partiel). Un port partiel peut être utile dans les cas où vous souhaitez simplement déplacer votre pont de conférence rendez-vous pour le service de conférence Audio.

Une commande port unique permettre transférer uniquement les numéros de téléphone à un type de numéro de téléphone unique. Si vous devez transférer certains de vos numéros de téléphone comme numéros d’abonné et d’autres en tant que numéro de service, nous vous recommandons d’abord effectuer le transfert à Microsoft puis effectuez la conversion dès qu’ils sont dans le contrôle de Microsoft.

Comme alternative, si le port partiel est pris en charge, vous pouvez envoyer plusieurs demandes de port, demande un port à la fois. Toutefois, cette méthode alternative sera prolonger votre contrat avec votre fournisseur de services de télécommunications existant.

Portage numéro de téléphone est un sujet complexe et nécessite une planification approfondie, coordination et correctement la gestion des attentes de votre des parties prenantes. Pour plus d’informations, voir les articles suivants :

-   [Transfert des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Questions fréquentes à propos du transfert de numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existant seront transférés vers Microsoft.</li><li>Choisir le type de numéros de téléphone à transférer à Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existant seront transférés vers Microsoft.</li><li>Le type de numéros de téléphone à transférer à Microsoft de document.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un Plan de numérotation dans la fonctionnalité de système téléphonique d’Office 365 est un ensemble de règles de normalisation qui traduit composé des numéros de téléphone dans un autre format (généralement le format E.164) pour l’autorisation d’appel et le routage des appels. Le service de conférence Audio exploite les mêmes capacités utilisées par le système téléphonique pour traduire des numéros de téléphone composé dans les scénarios d’appel sortant de conférence (par exemple, inviter des participants via PSTN et numérotation, fonctionnalité « m’appeler »).

Dans la fonction système téléphonique d’Office 365, il existe deux types de plans de numérotation :

-   **Plan de numérotation Service :** Il s’agit de la valeur par défaut plan de numérotation est appliquée aux utilisateurs en fonction de leur emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.

-   **Client au plan de numérotation :** Il s’agit d’un plan de numérotation personnalisable au sein d’un client, ce qui est divisé en deux types :

    -   **Client globales plan de numérotation :** Le plan de numérotation qui s’applique à tous les utilisateurs dans le client.

    -   **Plan de numérotation utilisateur client :** Le plan de numérotation qui s’applique uniquement à certains utilisateurs.

Le plan de numérotation effectives attribué aux utilisateurs est la combinaison du plan de numérotation service (basé sur l’emplacement d’utilisation d’un utilisateur Office 365) et plan de numérotation de client (peut être plan de numérotation global-client ou de plan de numérotation utilisateur client).

![Tableau présente trois combinaisons de service et les clients des plans de numérotation.] (media/audio_conferencing_image8.png "Tableau présente trois combinaisons de service et les clients des plans de numérotation.")

> [!Important]
> Il peut y avoir un maximum de 25 règles de normalisation dans chaque plan de numérotation client ; Par conséquent, il est important éviter la duplication des règles de normalisation qui sont déjà disponibles dans le cadre du service de plan de numérotation.

Pour en savoir plus sur les plans de numérotation, voir [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation nécessite des plans de numérotation personnalisé (impératifs d’entreprise, configuration requise d’adoption et ainsi de suite).</li><li>Le cas échéant, déterminez la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés.</li><li>Le cas échéant, décider des plans de numérotation client que vous créerez pour prendre en charge des bureaux ou emplacements de l’utilisateur dans la portée pour l’implémentation de la voix dans le nuage.</li><li>Le cas échéant, décider quels utilisateurs ont besoin d’un plan de numérotation personnalisé et le plan de numérotation client pour être attribué à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les plans de numérotation personnalisé et les règles de normalisation associées à configurer dans le cadre de votre implémentation de la voix dans le nuage.</li><li>Les utilisateurs à affecter à un plan de numérotation personnalisé et le plan de numérotation client pour être attribué à chaque utilisateur du document.</li></ul>|

> [!TIP]
> Si elle est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations de plan de numérotation client.
> 
> |Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000 â « x 8999) pour office OMB, Singapour_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 d’â « x 7999) pour 39 quai du Président Roosevelt office, les Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

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

## <a name="document-service-decisions"></a>Décisions de service de document 

Utilisez les informations dans les sections précédentes de cet article pour documenter vos décisions de service. En règle générale, cette documentation contient les sections principales suivantes :

-   Liste d’habilitations de sites pour le service d’audioconférence

-   Liste d’attributions de licences pour les organisateurs de réunions en audioconférence

-   Numéros de planification de crédits de communication

-   Détails du pont de téléconférence

-   Paramètres du pont de téléconférence

-   Affectations de paramètres de pont de téléconférence

-   Plans d’acquisition de numéros de téléphone

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->