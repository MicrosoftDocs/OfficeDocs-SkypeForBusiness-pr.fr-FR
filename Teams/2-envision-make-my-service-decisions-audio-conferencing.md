---
title: Rendre des décisions de service d’audioconférence - Teams Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: En savoir plus sur les réunions, le Gestionnaire de licences et la disponibilité, de configurer les paramètres de pont de conférence, d’acquérir ou de transfert des numéros de téléphone, de clients de choisir les plans d’appel.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa51cda9a9ce57d7672b152b45eb9c8e3cf4ba46
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de mon service

Pour planifier la mise en oeuvre technique des services de conférence Audio, vous devez effectuer une série de décisions de service à l’avance pour mieux préparer votre organisation pour implémenter une solution qui répond à vos besoins métier bien définis.

## <a name="audio-conferencing-in-teams"></a>Conférence audio dans des équipes

Dans le cadre de la définition des fonctionnalités d’audioconférence requises dans Teams de Microsoft, une des premières étapes consiste à évaluer du planning actualisé public pour déterminer :

-   Les fonctionnalités d’audioconférence dans des équipes qui seront déployées pour les utilisateurs dans la portée.

-   Prévu des exigences en matière de fonctionnalités utilisateur pour les conférences Audio dans des équipes.

-   Confirmation que les fonctionnalités d’audioconférence dans des équipes décrits dans le dernier programme public répondent à votre utilisateur, la fonctionnalité et les exigences de portée dans le montage de votre déploiement.

> [!NOTE]
> Le planning actualisé des équipes pour identifier les fonctionnalités de conférence Audio d’équipes dans la portée de votre déploiement, vous pouvez trouver à <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Réunions dans Teams

Équipes donne aux utilisateurs la possibilité de planifier et de participer à des conférences en ligne à l’aide de vidéo HD, les options d’accès à la conférence de la voix sur IP (VoIP) et RTC.

Les réunions peuvent être planifiées en tant que réunions privées (uniquement les parties invités peuvent joindre) ou des réunions de canal (ouvert pour tous les utilisateurs ayant accès au canal) et les utilisateurs peuvent également démarrer des réunions virtuelles impromptues dans les canaux.

> [!NOTE]
> Pour en savoir plus sur les fonctionnalités de réunions d’équipes, reportez-vous à la section [Skype pour entreprises à l’introduction de fonctionnalités Microsoft équipes] https://aka.ms/skype2teamsroadmap).

Participants à la réunion, vos réunions d’équipes peuvent joindre en appelant le numéro payant ou pont de conférence gratuit à distance via des réseaux terrestres ou les téléphones mobiles, les numéros de téléphone. En outre, les utilisateurs peuvent vous permettent du service d’audioconférence lancer la fonction « call me » afin qu’ils peuvent participer à une réunion en ayant le pont de conférence appeler leurs téléphones (utile lors de la connexion de données n’est pas fiable), ou la réunion permettent aux organisateurs invitation réunion participants par connexion à leur téléphone.

> [!IMPORTANT]
> Conférence audio dans des équipes ne prend pas en charge les fournisseurs de conférence audio de tiers (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilité de l’audioconférence

Avant de planifier la mise en oeuvre des services de conférence Audio dans des équipes, vous devez vérifier la disponibilité du service d’audioconférence comme détaillé dans le [pays et région de disponibilité pour les conférences Audio et les Plans d’appel](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> En raison des contraintes juridiques, pour les conférences Audio soient disponibles pour les organisations multinationales, le contrat pour les abonnements Office 365 doit provenir de pays et les régions où le service d’audioconférence est disponible dans le commerce.

Après avoir confirmé que votre organisation est éligible pour obtenir le service d’audioconférence, établissez la liste des emplacements de l’utilisateur ou des bureaux où vous allez implémenter le service d’audioconférence, en fonction de la liste des pays et régions disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements des utilisateurs ou les bureaux qui implémenteront le service d’audioconférence.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consignez les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service d’audioconférence.</li></ul>|

> [!TIP]
> Voici un exemple d’un modèle de liste de prise en charge Audio conférence site :
>|Bureau   |Emplacement |Service de conférence PSTN  |
>|---------|---------|---------|
>|1 Eppîng Road|Australie|Audioconférence|
>|100 Cyberport Road|Hong Kong R.A.S.|Conférence PSTN héritée|
>|1 Marina Boulevard|Singapour|Audioconférence|
>|32 London Bridge Street|Royaume-Uni|Audioconférence|
>|39 quai du Président Roosevelt|France|Audioconférence|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licences pour l’audioconférence

Une [licence d’audioconférence](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) est disponible dans le cadre de programmes d’abonnement Office 365 E5, ou sous la forme d’un service complémentaire aux plans d’abonnement Office 365 E1 ou Office 365 E3.

> [!NOTE]
> Conférence PSTN ou d’accès à distance dans des équipes ne prend pas en charge les fournisseurs de conférence audio de tiers (ACPs).
> <br>Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.

Pour fournir des numéros de téléphone de pont de conférence gratuit et prend en charge les conférences à distance à la sortie pour les numéros de téléphone internationaux, vous devez configurer [Les crédits de Communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) pour votre organisation.

> [!IMPORTANT]
> Certains pays sont traitées par les numéros de téléphone des pont de conférence gratuit uniquement. Pour prendre en charge à distance de ces pays, vous devez utiliser des crédits de Communications.

Le premier point important lors de la mise en œuvre de Communications crédits est de décider de la quantité initiale de fonds que vous souhaitez acheter. Si votre organisation choisit d’utiliser recharge automatique, vous devez décider le montant de déclencheur (montant minimal du fonds) et le montant de recharge automatique. L’activité réelle déterminera le montant recharge automatique. Vous devez surveiller l’utilisation des crédits de Communications dans le temps et ajuster le montant de recharge si nécessaire.

Pour en savoir plus sur les crédits de Communications [ici](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation n’a pas déjà acheté la licence de conférence Audio requis, décider si vous allez acquérir des licences d’audioconférence grâce au renforcement des abonnements Office 365 existantes ou à acquérir des licences supplémentaires d’audioconférence.</li><li>Décider si les crédits de Communications sont nécessaires pour votre implémentation d’audioconférence. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les utilisateurs qui recevront les licences audioconférence du document.</li><li>Documenter le plan de communication crédits (montant initial, montant de déclencheur, montant de recharge automatique)</li></ul>|

> [!TIP]
> Vous pouvez documenter la liste d’attribution de licence pour les utilisateurs d’audioconférence à l’aide de l’exemple suivant.
>|Utilisateur  |Bureau  |Licence Office 365  |
>|---------|---------|---------|
>|Adele Vance|1 Eppîng Road|Office 365 E5|
>|Alex Wilber|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
>|Ben Walters|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
>|Christie Cline|1 Marina Boulevard|Office 365 E3, complément pour l’audioconférence|
>|Debra Berger|1 Marina Boulevard|Office 365 E5|
>|Lee Gu|1 Marina Boulevard|Office 365 E5|
>|Emily Braun|32 London Bridge Street|Office 365 E5|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5|
>|Louis Lahr|32 London Bridge Street|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|

<br>
> [!TIP]
> Vous pouvez documenter les numéros de planification de vos crédits de communication comme suit :
>|         |         |
>|---------|---------|
>|Montant initial|1 000 $|
>|Montant déclencheur|400 $|
>|Montant de la recharge automatique|TBA|

<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Numéros de pont de téléconférence

Le service d’audioconférence dans Office 365 inclut les éléments suivants :

-   Plusieurs types de conférence pont entre les numéros de téléphone (numéro payant et gratuit)

-   Plusieurs catégories de pont de conférence de numéros (dédiés et partagés)

-   prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;

-   Un numéro de téléphone par défaut pour les clients

> [!NOTE]
> Conférence dédiée pont téléphone numéros s’inscrivent dans la limite des numéros de téléphone qui peuvent être acquises par les clients, en fonction du nombre de licences applicables. Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.

Si vous devez transférer des numéros de téléphone de pont conférence existants pour le service d’audioconférence, en supposant qu’ils les besoins spécifiques à un pays, vous pouvez transférer ces numéros de téléphone du pont conférence existante à Microsoft.

> [!NOTE]
La complexité de transfert des numéros de téléphone à Microsoft varie considérablement selon le pays ou la région, transporteur, nombre de circuits concernés et plusieurs autres facteurs. Auprès de votre fournisseur actuel pour déterminer combien de temps cela est susceptible de prendre pour s’assurer que vous commencez le processus dès le début de travail insuffisant répondre à vos montages.

Pour plus d’informations sur les numéros de téléphone de conférence pont, consultez les articles suivants :

-   [Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Numéros de téléphone pour l'audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtenir des numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Transférer des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si votre organisation a besoin de numéros de téléphone de pont de conférence dédiée.</li><li>Décider comment les numéros de téléphone de pont de conférence dédiée seront obtenus pour des bureaux ou des emplacements de l’utilisateur dans la portée de la mise en oeuvre d’Audio conférence (ce qui est, d’obtenir à partir de Microsoft ou transfert de numéros de téléphone existants).</li><li>Si vous choisissez de les obtenir auprès de Microsoft, choisissez la méthode à utiliser (l’envoi du formulaire ou automatique) pour les emplacements de l’utilisateur ou de bureaux dans la portée de la mise en oeuvre de l’audioconférence.</li><li>Choisir les préférences de langue pour définir pour chaque numéro de téléphone de pont de conférence dédiée.</li><li>Déterminez le numéro de téléphone de pont de conférence client par défaut.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter le plan général pour l’acquisition du numéro de téléphone, détaillant comment les numéros de téléphone seront obtenues pour chaque utilisateur ou office dans la portée de la mise en oeuvre de l’audioconférence.</li><li>Le cas échéant, complétez le formulaire nouvelle demande de numéro de téléphone, un seul formulaire pour chaque emplacement de bureau.</li><li>Document le pont de conférence détaillées de téléphone numéros configurations (partagé et dédié des numéros de téléphone de pont de conférence, les préférences de langue pour chaque numéro de téléphone de conférence dédiée bridge, numéro de téléphone de clients par défaut conférence bridge).</li></ul>|

Voici un exemple d’un modèle, que vous pouvez utiliser pour capturer des détails de pont de conférence.

> [!TIP]
> Voici un exemple de modèle pour capturer les détails du pont de téléconférence :
>|Bureau   |Acquisition de numéro de pont de téléconférence et type de pont |Numéro du pont  |Langue du pont|
>|---------|---------|---------|---------|
>|1 Eppîng Road|Acquisition d'un nouveau numéro de pont dédié|TBA|Anglais (Australie)|
>|1 Marina Boulevard|Acquisition d'un nouveau numéro de pont partagé|TBA|Anglais (États-Unis), Chinois (simplifié, RPC)|
>|32 London Bridge Street|Port existant, dédié|+44 20 7946 0001|Anglais (Royaume-Uni)|
>|39 quai du Président Roosevelt|Acquisition d'un nouveau numéro de pont dédié|TBA|Français (France), Anglais (Royaume-Uni)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Paramètres du pont de téléconférence

Pour personnaliser davantage l’expérience de l’utilisateur, vous pouvez configurer les options d’échelle de l’organisation pour joindre l’audioconférence réunions (entrée et sortie de notification et appelant nom d’enregistrement de la réunion), l’organisateur de la réunion longueur du code confidentiel et notification par e-mail :

-   Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.

-   La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.

-   Notification d’e-mails envoyés sur l’activation de la licence d’audioconférence ou toute autre modification contrôlée par l’administrateur sont activés par défaut. Vous pouvez désactiver cette fonctionnalité et prendre le contrôle des communications des utilisateurs de votre organisation.

Pour les utilisateurs qui ont une licence d’Audio conférence, les numéros par défaut numéro payant/toll-free, indiqués dans les coordonnées d’audioconférence, peuvent être configurés pour utiliser :

-   La valeur par défaut au niveau des clients.

-   Les numéros de téléphone de pont de conférence attribué automatiquement.

-   Numéros de téléphone de la passerelle conférence configuré manuellement pour chaque utilisateur.

Conférence de spécifiques à l’utilisateur de pont téléphone numéros sont généralement utiles pour les entreprises globales ou au niveau national, où les utilisateurs sont distribués et qu’il doivent fournir des numéros locaux comme les numéros de téléphone de pont de conférence par défaut dans les invitations à une réunion.

Participants qui la rejoignent à partir de différentes villes ou à l’étranger peuvent rechercher des numéros supplémentaires configurées au niveau du client, mais ces chiffres ne s’affichent pas directement dans les invitations aux réunions. Invitations à la réunion fournissent un lien qui mène les participants vers la page **numéros d’équipes de conférence** pour pouvoir rechercher le numéro de téléphone conférence pont le plus proche de leur emplacement.

Vous pouvez également configurer des appelants comment non authentifiés sont gérés par chaque organisateur individuels — si l’organisateur de la réunion pour démarrer la réunion avant les appelants non authentifiés peuvent être admis, ou autorisent est nécessaire non authentifié d’appelants pour démarrer une réunion .

Vous pouvez également appliquer des configurations supplémentaires pour chaque utilisateur afin de contrôler l’utilisation des numéros de téléphone de pont de conférence gratuit et les appels sortants à partir d’une conférence.

> [!NOTE]
> Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces. Vous pouvez inscrire votre organisation dans le programme Aperçu à partir de https://www.skypepreview.com.

Avec ces contrôles, vous pouvez décider si les organisateurs de la réunion peuvent fournir des numéros de téléphone de pont de conférence gratuit pour les réunions organisées par les et les participants peuvent Numéroter à partir de réunions qu’ils organisées. Le niveau de contrôle d’appels sortants étendues empêchent complètement les appels sortants, pour autoriser uniquement les appels sortants aux numéros nationaux, ou autoriser les appels sortants aux numéros nationaux et internationaux.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si votre organisation requiert des notifications d’entrée et de sortie, et, si c’est le cas, le type de notification à mettre en oeuvre (tonalités, numéro de téléphone ou nom enregistré).</li><li>Décidez de la longueur de la broche de conférence Audio qui répond à vos besoins de sécurité de l’organisation.</li><li>Décidez si votre organisation souhaite prendre le contrôle des communications des utilisateurs liés au service d’audioconférence.</li><li>Déterminez les numéros de pont de téléconférence à attribuer à chaque organisateur de réunions.</li><li>Décider si certains organisateurs de la réunion doivent utiliser des numéros de téléphone de pont de conférence gratuit pour leurs réunions.</li><li>Décider si certains organisateurs de la réunion est nécessaire permettre à des appelants non authentifiés démarrer une réunion.</li><li>Décider si certains organisateurs de réunions doivent composer en sortie de conférence à contrôler.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration)</li><li>Les numéros de téléphone de pont de conférence pour être affectée à chaque organisateur de la réunion et le paramètre correspondant à la stratégie de contrôle pour les appelants non authentifiés et gratuit de documents et de composer des contrôles.</li></ul>|

> [!TIP]
> Vos paramètres de pont de conférence peuvent être décrite comme dans l’exemple suivant.
>|         |         |
>|---------|---------|
>|Activer les notifications d’accès et de sortie de réunion|Activé|
>|Type d’annonce d’accès/sortie|Tonalités|
>|Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion|Désactivé|
>|Longueur du code PIN|5|
>|Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de numérotation changent|Désactivé|

<br>
> [!TIP]
> Vous pouvez documenter la liste d’affectation de paramètres de conférence pont pour les utilisateurs d’audioconférence à l’aide de l’exemple suivant.
>|Utilisateur  |Bureau  |Numéro payant par défaut  |Numéro gratuit par défaut  |Autoriser le numéro gratuit  |Les appelants non authentifiés contournent la salle d’attente  |Composition de numéros depuis la conférence  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|1 Eppîng Road|TBA|TBA|Oui|Activé|Internationaux et nationaux|
>|Alex Wilber|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
>|Ben Walters|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
>|Christie Cline|1 Marina Boulevard|TBA|TBA|Oui|Désactivé|Nationaux|
>|Debra Berger|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
>|Lee Gu|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
>|Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Activé|Non autorisé|
>|Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
>|Louis Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
>|Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|
>|Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Oui|Activé|Internationaux et nationaux|
>|Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone vocal de nuage

Pour la mise en oeuvre de la conférence de l’Audio, vous pouvez choisir à acquérir de nouveaux numéros de téléphone ou les numéros de téléphone existants de transfert/port.

Pour permettre aux utilisateurs de composer les numéros de téléphone de la façon dont ils sont habitués à — en omettant les codes de zone pour les appels locaux, en omettant le code de pays pour les appels nationaux ou même à l’aide de chiffres court de numérotation lors de la conférence, appels sortants, vous pouvez configurer un plan de numérotation personnalisé et l’affecter à des utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquérir de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions de voix de nuage de Microsoft sont les suivantes :

-   Numéros d’abonné (utilisateur), qui peuvent être assignés aux utilisateurs de votre organisation.

-   Numéros de service disponibles en tant que numéro payant et les numéros de service gratuit, qui ont la capacité d’appel simultané plus élevée que les chiffres de l’abonné et peuvent être affectés aux services d’audioconférence, des surveillances automatiques ou des files d’attente de l’appel.

Pour plus d’informations sur ces types de numéros de téléphone, voir [différents types de numéros de téléphone utilisés pour les Plans d’appel](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Nombre total d’appels téléphoniques que vous pouvez obtenir les numéros varient selon les types de numéros de téléphone et le nombre de licences que vous avez achetées et affectées à vos utilisateurs.

Lorsqu’il s’agit du numéro de service, vous devez planifier avec soin votre mise en œuvre de l’audioconférence. Déterminez si votre entreprise requiert des numéros de téléphone du pont de conférence dédiée ; Si ce n’est pas le cas, votre organisation peut choisir d’utiliser des numéros de téléphone de pont de conférence partagé.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, consultez [le nombre de numéros de téléphone vous obtiendrez ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir les emplacements de l’utilisateur ou les bureaux où les nouveaux numéros de téléphone seront sont acquis à partir de Microsoft.</li><li>Choisir le type de numéros de téléphone à acquérir auprès de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les nouveaux numéros de téléphone seront sont acquis à partir de Microsoft.</li><li>Le type de numéros de téléphone à acquérir de Microsoft de document.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfert des numéros de téléphone existant

Si votre organisation souhaite de transfert (ou port) existant à Microsoft, les numéros de téléphone, vous pouvez le faire en envoyant une demande de commande de port à Microsoft.

Vous pouvez transférer tous vos existant téléphone numéros à la fois (port complet), et, sur certains marchés, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existant (port partielle). Un port partiel peut être utile dans les cas où vous souhaitez simplement déplacer votre pont de conférences au service d’audioconférence.

Une commande port unique peut uniquement transférer les numéros de téléphone à un type de numéro de téléphone unique. Si vous devez transférer certaines de vos numéros de téléphone sous forme de numéros de l’abonné, ainsi que sous forme de numéros de service, nous vous recommandons que vous tout d’abord complétez le transfert à Microsoft et que vous effectuez la conversion dès qu’ils sont dans le contrôle de Microsoft.

Comme alternative, si port partielle est pris en charge, vous pouvez soumettre plusieurs demandes du port, demande un port à la fois. Toutefois, cette approche alternative de se prolonger votre contrat avec votre fournisseur de services de télécommunications existants.

Portage numéro de téléphone est un sujet complexe et requiert une planification minutieuse, de coordination et suffisamment gestion des attentes de vos parties prenantes. Pour plus d’informations, consultez les articles suivants :

-   [Transfert des numéros de téléphone à Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Questions fréquentes à propos du transfert de numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir les emplacements utilisateur ou les bureaux où les numéros de téléphone existants seront transférés à Microsoft.</li><li>Choisir le type de numéros de téléphone pour être transférés à Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existants seront transférés à Microsoft.</li><li>Le type de numéros de téléphone pour être transférés à Microsoft de document.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un Plan de numérotation dans la fonction système téléphonique d’Office 365 est un ensemble de règles de normalisation qui traduit composé des numéros de téléphone dans un autre format (en général le format E.164) pour le routage des appels et l’autorisation d’appel. Le service d’audioconférence exploite les mêmes fonctionnalités que celui utilisées par le système téléphonique pour convertir les numéros de téléphone composés dans les scénarios d’appel sortant de conférence (par exemple, inviter des participants via RTPC et accès à distance, fonction de « call me »).

Dans la fonction système téléphonique d’Office 365, il existe deux types de plans de numérotation :

-   **Plan d’appel de Service :** Il s’agit de la valeur par défaut plan de numérotation qui est appliquée aux utilisateurs en fonction de leur emplacement de l’utilisation d’Office 365, et il ne peut pas être modifié.

-   **Plan d’appel de clients :** Il s’agit d’un plan d’appel personnalisables dans un client, ce qui est divisé en deux types :

    -   **Plan de numérotation de clients globale :** Le plan de numérotation qui s’applique à tous les utilisateurs dans le locataire.

    -   **Plan de numérotation de client-utilisateur :** Le plan de numérotation qui s’applique uniquement à certains utilisateurs.

Plan de numérotation effectives attribué aux utilisateurs est la combinaison du service à distance plan (basé sur l’emplacement d’utilisation d’un utilisateur Office 365) et plan de numérotation de clients (ce peut être soit plan de numérotation globale locataire ou plan de numérotation de client-utilisateur).

![Tableau montre trois combinaisons de service et les clients des plans de numérotation.] (media/audio_conferencing_image8.png "Tableau montre trois combinaisons de service et les clients des plans de numérotation.")

> [!Important]
> Il peut y avoir un maximum de 25 règles de normalisation dans chaque plan de numérotation de clients ; Par conséquent, il est important d’éviter de dupliquer les règles de normalisation qui sont déjà disponibles dans le cadre du service de plan de numérotation.

Pour en savoir plus sur les plans de numérotation, consultez [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si votre organisation requiert que les plans de numérotation personnalisé (besoins, exigences en matière d’adoption et ainsi de suite).</li><li>Le cas échéant, déterminez la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés.</li><li>Le cas échéant, décider des plans de numérotation de clients que vous allez créer pour prendre en charge des bureaux ou des emplacements de l’utilisateur dans la portée de la mise en oeuvre des voix de nuage.</li><li>Le cas échéant, décider que les utilisateurs qui nécessitent un plan de numérotation personnalisé et le plan de numérotation de clients à affecter pour chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les plans de numérotation personnalisé et les règles de normalisation associé à configurer dans le cadre de votre implémentation de voix de nuage.</li><li>Documenter les utilisateurs pour être affecté à un plan de numérotation personnalisé et le plan de numérotation de clients à affecter pour chaque utilisateur.</li></ul>|

> [!TIP]
> S’il est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations de plan d’accès clients.
>|Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000 â « x 8999) pour office OMB, Singapour_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 â €« x 7999) pour 39 quai du Président Roosevelt office Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>|Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
>|---------|---------|---------|---------|
>|Adele Vance|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Alex Wilber|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Ben Walters|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Christie Cline|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Debra Berger|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Lee Gu|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Louis Lahr|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions de service de document 

Utilisez les informations dans les sections précédentes de cet article pour documenter vos décisions de service. En général, cette documentation contient les sections suivantes :

-   Liste d’habilitations de sites pour le service d’audioconférence

-   Liste d’attributions de licences pour les organisateurs de réunions en audioconférence

-   Numéros de planification de crédits de communication

-   Détails du pont de téléconférence

-   Paramètres du pont de téléconférence

-   Affectations de paramètres de pont de téléconférence

-   Les plans d’acquisition des numéros de téléphone

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->