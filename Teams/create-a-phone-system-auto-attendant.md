---
title: Configurer un standard automatique pour Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
ms.custom:
- Phone System
description: Découvrez comment configurer et gérer des standards automatiques dans Microsoft Teams.
ms.openlocfilehash: 913ac62ceb251f166852ec8c6d5ba84b7c0777ea
ms.sourcegitcommit: 850038f2248c1ea412f7b5daca26c0598baffa3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2022
ms.locfileid: "67443401"
---
# <a name="set-up-an-auto-attendant"></a>Configurer un standard automatique

Les standards automatiques permettent aux utilisateurs d’appeler votre organisation et de naviguer dans un système de menus pour parler au service approprié, à la file d’attente des appels, à une personne ou à un opérateur. Vous pouvez créer des standards automatiques pour votre organisation avec le Centre d’administration Microsoft Teams ou PowerShell.

Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.

Les standards automatiques peuvent rediriger les appels, en fonction de l’entrée des appelants, vers l’une des destinations suivantes :

- **Opérateur** : opérateur défini pour le standard automatique. La définition d’un opérateur est facultative. L’opérateur peut être défini comme l’une des autres destinations de cette liste.
- **Personne de l’organisation** : une personne de votre organisation qui peut recevoir des appels vocaux. Cette personne peut être un utilisateur en ligne ou un utilisateur hébergé localement à l’aide de Skype Entreprise Server.
- **Application vocale** : un autre standard automatique ou une file d’attente d’appels. (Choisissez le compte de ressource associé au standard automatique ou à la file d’attente d’appels lors du choix de cette destination.)
- **Messagerie vocale** : boîte aux lettres vocale associée à un groupe Microsoft 365 que vous spécifiez. Vous pouvez choisir si vous voulez des transcriptions de messagerie vocale et le message « Veuillez laisser un message après le ton ». invite système.
  - Dans M365 Administration Center, activez « Autoriser les personnes extérieures à l’organisation à envoyer un e-mail à cette équipe » pour le groupe Microsoft 365 que vous spécifiez
- **Numéro de téléphone externe** : n’importe quel numéro de téléphone. Consultez [les détails techniques du transfert externe](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details).
- **Annonce (fichier audio)** : lire un fichier audio. Message d’annonce enregistré que vous chargez qui est enregistré en tant qu’audio dans . WAV, .MP3 ou . Format WMA. L’enregistrement ne peut pas dépasser 5 Mo. Le système lit l’annonce, puis revient au menu du standard automatique.
- **Annonce (Typée)** : tapez un message. Texte que vous souhaitez que le système lisent. Vous pouvez entrer jusqu’à 1 000 caractères. Le système lit l’annonce, puis revient au menu du standard automatique.

> [!NOTE]
> Lorsque vous redirigez des appels vers une **personne de l’organisation**, cette personne doit être activée par la voix. Pour plus d’informations sur l’activation de la voix, consultez [Affecter des licences de module complémentaire Teams aux utilisateurs](teams-add-on-licensing/assign-teams-add-on-licenses.md).
>
> Bien que la définition d’un **opérateur** soit facultative, elle est recommandée.  Les standards automatiques redirigent les appels vers l’opérateur si l’appelant n’effectue pas de sélection sur les menus, sélectionne à plusieurs reprises des options non valides ou si les appels par nom ou numéro échouent à plusieurs reprises.  Si aucun opérateur n’est défini, le standard automatique supprime l’appel.

## <a name="whats-new-for-auto-attendants-in-the-past-6-months"></a>Nouveautés des standards automatiques au cours des 6 derniers mois
 
 - Août - **Les options de menu Lire** dans le flux d’appel, le flux d’appel pour les heures creuses et le flux d’appel pendant les jours fériés prennent désormais en charge \* les clés (astérisque) et \# (livre).
 - Juillet - Le flux d’appels pendant les jours fériés prend désormais en charge les **options de menu Lecture**.
 
## <a name="steps-to-create-an-auto-attendant"></a>Étapes de création d’un standard automatique

Les étapes à suivre pour ajouter un standard automatique sont les suivantes :

1. Configurez des informations générales.
1. Configurez un flux d’appel de base.
1. Configurez un flux d’appels après heures.
1. Configurez les flux d’appels de congés.
1. Configurez l’étendue de numérotation.
1. Configurez des comptes de ressources.

Les étapes décrites dans l’article créent des standards automatiques à l’aide du Centre d’administration Teams. Pour obtenir des instructions sur la **création de standards automatiques à l’aide de PowerShell**, consultez [Création de standards automatiques avec des applets de commande PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Suivez ces étapes pour configurer votre standard automatique

# <a name="step-1-general-info"></a>[Étape 1 : Informations générales](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>Étape 1 : Définir les informations générales du standard automatique

Pour configurer un standard automatique, dans le [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851), développez **Voix**, sélectionnez **Standards automatiques**, puis **Sélectionnez Ajouter**.

1. Tapez un nom pour le standard automatique dans la zone située en haut.

2. Pour désigner un opérateur, spécifiez la destination des appels à l’opérateur. Cette désignation est facultative, mais recommandée. Définissez l’option **Opérateur** pour permettre aux appelants de sortir des menus et de parler à une personne désignée.

3. Spécifiez le fuseau horaire de ce standard automatique. Le fuseau horaire est utilisé pour calculer les heures d’ouverture si vous [créez un flux d’appels distinct pour les heures supplémentaires](?tabs=after-hours).

4. Spécifiez une [langue prise en charge](create-a-phone-system-auto-attendant-languages.md) pour ce standard automatique. Il s’agit du langage qui sera utilisé pour les invites vocales générées par le système.

5. Choisissez si vous souhaitez activer les entrées vocales. Lorsque cette option est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale. Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée à la clé 1, ou ils peuvent dire « Ventes » pour sélectionner l’option de menu nommée « Ventes ».

   > [!NOTE]
   > Si vous choisissez une langue à l’étape 4 qui ne prend pas en charge les entrées vocales, cette option est désactivée.

Une fois que vous avez défini les informations générales de votre standard automatique, sélectionnez **Suivant**.

# <a name="step-2-basic-call-flow"></a>[Étape 2 : Flux d’appel de base](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>Étape 2 : Configurer le flux d’appel de base

### <a name="set-a-greeting"></a>Définir un message d’accueil

- Si vous **sélectionnez Lire un fichier audio** , vous pouvez utiliser le bouton **Charger un fichier** pour charger un message d’accueil enregistré enregistré sous forme audio. WAV, .MP3 ou . Format WMA. L’enregistrement ne peut pas dépasser 5 Mo.

- Si vous sélectionnez **Tapez un message d’accueil** , le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque le standard automatique répond à un appel.

### <a name="route-the-call"></a>Router l’appel

- Si vous sélectionnez **Déconnecter**, le standard automatique raccroche l’appel.
- Si vous sélectionnez **l’appel de redirection**, vous pouvez choisir l’une des destinations de routage des appels.
- Si vous **sélectionnez les options de menu Lecture**, vous pouvez choisir **de lire un fichier audio** ou **de taper un message d’accueil** , puis de choisir entre les options de menu et la recherche dans le répertoire.

#### <a name="play-menu-options"></a>Options de menu Lecture

*Les clés New - \* (astérisque) et \# (livre) peuvent désormais être utilisées dans les options de menu.*

Pour les options de numérotation, affectez les touches 0-9, \* (astérisque) et \# (livre) sur le clavier téléphonique à l’une des destinations de routage des appels. 

Les mappages de clés ne doivent pas nécessairement être continus. Il est possible de créer un menu avec les clés 0, 1 et 3 mappées aux options, tandis que la clé numéro 2 n’est pas utilisée.

Nous vous recommandons de mapper la clé zéro à l’opérateur si vous en avez configuré une. Si l’opérateur n’est défini sur aucune clé, la commande vocale « Opérateur » est également désactivée.

Pour chaque option de menu, spécifiez les paramètres suivants :

- **Clé de numérotation** : clé sur le clavier téléphonique pour accéder à cette option. Si des entrées vocales sont disponibles, les appelants peuvent également indiquer ce numéro pour accéder à l’option.

- **Commande vocale** : définit la commande vocale qu’un appelant peut donner pour accéder à cette option, si les entrées vocales sont activées. Il peut contenir plusieurs mots tels que « Service clientèle » ou « Opérations et motifs ». Par exemple, l’appelant peut appuyer sur 2, dire « deux » ou « Ventes » pour sélectionner l’option mappée aux deux clés. Ce texte est également affiché par synthèse vocale pour l’invite de confirmation de service, qui peut être quelque chose comme « Transfert de votre appel aux ventes ».

- **Rediriger vers** la destination de routage des appels utilisée lorsque les appelants choisissent cette option. Si vous effectuez une redirection vers un standard automatique ou une file d’attente d’appels, choisissez le compte de ressource qui lui est associé.

##### <a name="directory-search"></a>Recherche dans l’annuaire

Si vous attribuez des clés de numérotation à des destinations, nous vous recommandons de choisir **Aucun** pour **la recherche dans l’annuaire**. Si un appelant tente de composer un nom ou une extension à l’aide de clés affectées à des destinations spécifiques, il peut être routée de manière inattendue vers une destination avant de terminer d’entrer le nom ou l’extension. Nous vous recommandons de créer un standard automatique distinct pour la recherche dans l’annuaire et d’y associer votre standard automatique principal avec une clé de numérotation.

Si vous n’avez pas affecté de clés de numérotation, choisissez une option pour **la recherche dans l’annuaire**.

**Numérotation par nom** : si vous activez cette option, les appelants peuvent indiquer le nom de l’utilisateur ou le taper sur le clavier téléphonique. Tout utilisateur en ligne ou tout utilisateur hébergé localement à l’aide de Skype Entreprise Server est un utilisateur éligible et peut être trouvé avec Dial par nom.

**Numérotation par extension** : si vous activez cette option, les appelants peuvent se connecter aux utilisateurs de votre organisation en composant leur extension téléphonique. Tout utilisateur en ligne ou tout utilisateur hébergé localement à l’aide de Skype Entreprise Server est un utilisateur éligible et peut être trouvé avec **Dial par extension**. (Vous pouvez définir qui est et n’est pas inclus dans le répertoire de la page [d’étendue De numérotation](?tabs=dial-scope) .)

> [!NOTE]
> Si vous souhaitez utiliser les fonctionnalités **Numérotation par nom** et **Numérotation par extension** , vous pouvez affecter une clé de numérotation sur votre standard automatique principal pour atteindre un standard automatique activé pour **Dial par nom**. Dans ce standard automatique, vous pouvez affecter la touche 1 (qui n’a aucune lettre associée) pour atteindre le standard automatique **Dial by extension** .

Pour plus d’informations, reportez-vous à la [référence Numérotation et voix](dial-voice-reference.md).

Une fois que vous avez défini vos options de flux d’appel de base, sélectionnez **Suivant**.

# <a name="step-3-after-hours-call-flow"></a>[Étape 3 : Flux d’appels après heures](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>Étape 3 : Configurer le flux d’appels après les heures de travail (facultatif)

Les heures d’ouverture peuvent être définies pour chaque standard automatique.

- Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut.
- Les heures d’ouverture peuvent être définies avec des pauses dans le temps pendant la journée, et toutes les heures qui ne sont pas définies en tant qu’heures d’ouverture sont considérées comme après les heures d’ouverture.
- Vous pouvez définir différentes options de gestion des appels entrants et des messages d’accueil pour les heures d’après-midi.

Selon la façon dont vous avez configuré vos standards automatiques et vos files d’attente d’appels, vous devrez peut-être uniquement spécifier le routage des appels après les heures d’ouverture pour les standards automatiques avec des numéros de téléphone directs.

Si vous souhaitez séparer le routage des appels pour les appelants après les heures d’ouverture, spécifiez vos heures d’ouverture pour chaque jour.

1. En regard du jour de la semaine dans le tableau, **ajustez le début et** la **fin à certains** moments.
1. Si nécessaire, **sélectionnez Ajouter une nouvelle heure** pour spécifier plusieurs ensembles d’heures pour un jour donné, par exemple, pour spécifier une pause déjeuner.
1. Choisissez les options de routage des appels pour les heures supplémentaires. Les mêmes options de flux d’appel générales sont également disponibles après les heures d’ouverture.

Une fois que vous avez ajouté votre flux d’appels après heures, sélectionnez **Suivant**.

# <a name="step-4-holiday-call-flow"></a>[Étape 4 : Flux d’appels de vacances](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>Étape 4 : Configurer des flux d’appels pour les jours fériés (facultatif)

Votre standard automatique peut avoir un flux [d’appels pour chaque congé que vous avez configuré](set-up-holidays-in-teams.md). Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

*Nouveau : **les options de menu Lecture** sont désormais disponibles dans les flux d’appels de vacances.*

1. Dans la page Paramètres de l’appel de congés, sélectionnez **Ajouter**.

1. Tapez un nom pour ce paramètre de congé.

1. Dans la liste **déroulante Vacances** , choisissez les vacances que vous souhaitez utiliser.

1. Choisissez le type de message d’accueil que vous souhaitez utiliser.

1. Choisissez si vous souhaitez **déconnecter**, **rediriger** ou **lire les options de menu** de l’appel.

    1. Si vous avez choisi de rediriger, choisissez la destination de routage des appels pour l’appel.
    1. Si vous choisissez de lire des options de menu, **configurez les options de menu Lecture**.

1. Sélectionnez **Enregistrer**.

Répétez la procédure en fonction des besoins pour chaque congé supplémentaire.

Une fois que vous avez ajouté toutes vos heures de congé, sélectionnez **Suivant**.

# <a name="step-5-dial-scope"></a>[Étape 5 : Étendue de numérotation](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>Étape 5 : Configurer l’étendue de numérotation (facultatif)

*L’étendue de numérotation* définit les utilisateurs disponibles dans le répertoire lorsqu’un appelant utilise le numérotation par nom ou numérotation par extension. La valeur par défaut de **Tous les utilisateurs en ligne** inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne ou hébergés localement à l’aide de Skype Entreprise Server.

Vous pouvez inclure ou exclure des utilisateurs spécifiques en sélectionnant Groupe **d’utilisateurs personnalisé** sous **Inclure** ou **Exclure** et en choisissant un ou plusieurs groupes Microsoft 365, listes de distribution ou groupes de sécurité. Par exemple, vous souhaiterez peut-être exclure les cadres de votre organisation du répertoire de numérotation.

Si un utilisateur se trouve dans les deux listes, il est exclu du répertoire.

> [!NOTE]
> Le nom d’un nouvel utilisateur peut prendre jusqu’à 36 heures dans le répertoire.

Une fois que vous avez sélectionné vos options **d’étendue de numérotation** , sélectionnez **Suivant**.

# <a name="step-6-resource-accounts"></a>[Étape 6 : Comptes de ressources](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>Étape 6 : Configurer des comptes de ressources (facultatif)

Tous les standards automatiques doivent avoir un compte de ressources associé.  Les standards automatiques de premier niveau auront besoin d’au moins un compte de ressource associé à un numéro de service. Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un standard automatique, chacun avec un numéro de service distinct.

Pour ajouter un compte de ressource, sélectionnez **Ajouter un compte** et recherchez le compte que vous souhaitez ajouter. Sélectionnez **Ajouter**, puis **sélectionnez Ajouter**.

Une fois que vous avez ajouté des comptes de ressources, sélectionnez **Suivant**.

Pour plus d’informations, consultez [Gérer les comptes de ressources Teams](manage-resource-accounts.md) .

---

## <a name="resources-for-complex-scenarios"></a>Ressources pour des scénarios complexes

### <a name="external-phone-number-transfers---technical-details"></a>Transferts de numéros de téléphone externes - Détails techniques

Reportez-vous aux [conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) pour autoriser les standards automatiques à transférer des appels en externe.  De plus,:

- Pour un compte de ressource avec une [licence forfait d’appels](calling-plans-for-office-365.md) ou un numéro [de connexion d’opérateur](operator-connect-plan.md) , le numéro de téléphone de transfert externe doit être entré au format E.164 (+[code du pays][indicatif régional][numéro de téléphone]).

- Pour un compte de ressource avec une stratégie de routage vocal en ligne de licence Téléphonie Microsoft Teams et de routage direct, le format de numéro de téléphone de transfert externe dépend des paramètres [du contrôleur de frontière de session (SBC](direct-routing-connect-the-sbc.md)).

Le numéro de téléphone sortant affiché est déterminé comme suit :

- Pour les numéros de plan d’appel et de connexion d’opérateur, le numéro de téléphone de l’appelant d’origine s’affiche.
- Pour les numéros de routage direct, le nombre envoyé est basé sur le paramètre P-Asserted-Identity (PAI) sur le SBC, comme suit :
  - Si la valeur est Désactivée, le numéro de téléphone de l’appelant d’origine s’affiche. Il s’agit du paramètre par défaut et recommandé.
  - Si la valeur est Activée, le numéro de téléphone du compte de ressource s’affiche.

Dans un environnement hybride Skype Entreprise, pour transférer un appel de standard automatique au rtc, créez un utilisateur local avec le transfert d’appel défini sur le numéro RTC. L’utilisateur doit être activé pour Téléphonie –  Grandes entreprises et une stratégie de voix doit être affectée. Pour plus d’informations, consultez [Transfert d’appel du standard automatique vers PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Outil de diagnostic du standard automatique

Si vous êtes administrateur, vous pouvez utiliser l’outil de diagnostic suivant pour vérifier qu’un standard automatique est en mesure de recevoir des appels :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365.

   > [!div class="nextstepaction"]
   > [Exécuter des tests : Standard automatique Teams](https://aka.ms/TeamsAADiag)

2. Dans le volet De diagnostic d’exécution, entrez le compte de ressource dans le champ **Nom d’utilisateur ou Email**, puis sélectionnez **Exécuter les tests**.

3. Les tests identifient les configurations de locataire, de stratégie ou de compte de ressource qui empêchent le standard automatique de recevoir des appels et fournissent des étapes pour résoudre les problèmes identifiés.

### <a name="related-topics"></a>Rubriques connexes

[Voici ce que vous obtenez avec Teams Phone](./here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](./getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
