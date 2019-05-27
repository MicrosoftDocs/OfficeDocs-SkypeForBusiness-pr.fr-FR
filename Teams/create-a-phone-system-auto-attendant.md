---
title: Configurer un standard automatique dans le cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Apprenez à configurer et tester des standards automatiques Cloud pour gérer efficacement les appels pour votre organisation.
ms.openlocfilehash: 892285e2e720e300d9b935f017dedca96e45b411
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432895"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurer un standard automatique dans le cloud

Les standards automatiques permettent aux personnes qui rejoignent votre organisation d’appeler votre organisation et de naviguer dans un système de menu pour les faire passer au service approprié, à la file d’attente des appels, à la personne ou à l’opérateur. Vous pouvez créer un standard automatique pour votre organisation à l’aide du centre d’administration Microsoft Teams. Pour créer un standard automatique, dans la barre de navigation gauche, sélectionnez **voix** , puis cliquez sur **standards** > automatiques**Ajouter nouveau**.

Pour en savoir plus sur les standards automatiques, reportez-vous à la rubrique [qu’est-ce que les standards automatiques Cloud?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online.



## <a name="step-1---get-started"></a>Étape 1: commencer

- Un standard automatique est requis pour disposer d’un compte de ressources associé. Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .
- Si vous envisagez d’affecter un numéro d’acheminement direct, vous devez acquérir et attribuer les licences suivantes à \(votre compte de ressources Office 365 entreprise E1, E3 ou E5, à l’aide\)du composant additionnel du système téléphonique.
- Si vous affectez un numéro de service Microsoft à la place, vous devez acquérir et attribuer les licences suivantes à votre compte \(de ressources Office 365 entreprise E1, E3 ou E5, avec le module complémentaire du système téléphonique et un\)plan d’appels.

> [!NOTE] 
> Microsoft travaille sur un modèle de licence sans frais pour des applications telles que les standards automatiques de Cloud et les files d’attente d’appels, pour le moment, vous devez utiliser le modèle de gestion des licences utilisateur.

> [!CAUTION]
> Pour obtenir et utiliser des numéros de téléphone gratuits, vous devez configurer des crédits de communication. Pour faire cela, consultez [Quelles sont les Communications crédits ?](what-are-communications-credits.md) et [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).

> [!TIP]
> Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne disposant d’une licence de **système téléphonique** , vous devez l’activer pour Enterprise Voice ou affecter des plans d’appel dans Office 365. Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [affectation de licences Microsoft teams](assign-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Étape 2 : création d'un standard automatique

> [!IMPORTANT]
> Chaque standard automatique doit disposer d’un compte de [ressources](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer au standard automatique.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft teams

Dans le **Centre d’administration de Microsoft teams**, cliquez sur**standards automatiques** **vocaux** > , puis sur **+ nouveau**:

#### <a name="general-info-page"></a>Page informations générales

![Capture d’écran de la page mon standard automatique](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

**Nom** Entrez un nom descriptif pour le standard automatique. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Il sera répertorié dans la colonne **Nom** de l'onglet **Standards automatiques**.

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

**Compte de ressources** Cliquez sur ce bouton pour sélectionner un ou plusieurs comptes de ressources pour vous connecter à votre nouveau standard automatique. Tous les standards automatiques doivent disposer d’un compte de ressources associé. Un compte de ressource peut avoir un numéro de téléphone associé au compte, mais ce n’est pas le tout. Le standard automatique de niveau supérieur possède généralement un compte de ressources avec un numéro de téléphone attribué, mais le standard automatique imbriqué (utilisé en tant que menu de niveau 2 auquel le standard automatique de premier niveau est connecté) peut ne pas avoir de numéro de téléphone attribué à son compte de ressources.

* * *

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.

* * *

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées. La langue que vous définissez ici correspond à la langue que le standard automatique utilisera pour interagir avec les personnes qui rejoignent le standard automatique et toutes les invites système seront exécutées dans cette langue.

* * *

![Icône du numéro 5 qui référence une légende dans la capture d’écran précédente](media/sfbcallout5.png)

**Opérateur** Cette option est facultative ne doit pas nécessairement être définie pour le standard automatique. Toutefois, vous pouvez définir l’option d' **opérateur** pour les personnes qui appellent pour être en mesure de sortir du menu pour parler à une personne.

La touche 0 est automatiquement affectée à l'option Opérateur.

Si vous configurer ce paramètre, vous devez également indiquer aux personnes qui appellent que ceci est une option disponible dans le **menu options d’édition** dans la page **Gestion des appels en heures** . Si vous définissez un opérateur pour le standard automatique, vous devrez entrer le texte du message correspondant dans la zone **appelants entendront** ou modifier votre fichier audio pour inclure cette option. Par exemple, « pour l’opérateur, appuyez sur zéro. »

L'opérateur peut être défini comme suit :

- **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365.

     > [!Note]
     > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.

- Une **file d’attente d’appels** que vous avez configurée.
- Vous pouvez la configurer de manière qu'une personne appelant soit renvoyée sur la messagerie. Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez les appels de cette personne pour qu’elle soit transférée directement vers la messagerie vocale.

* * *

![Icône du numéro 6 qui référence une légende dans la capture d’écran précédente](media/sfbcallout6.png)

**Activer les entrées vocales** La reconnaissance vocale est disponible si cette option est sélectionnée. Les personnes qui appellent dans peuvent utiliser la saisie vocale dans la [langue que vous avez définie](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Vous pouvez désactiver la reconnaissance vocale en la définissant sur désactivé si vous souhaitez uniquement permettre aux utilisateurs d’utiliser leur clavier téléphonique.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="business-hours-page"></a>Page heures de bureau

Par défaut, les heures d’activité sont définies sur 9H à 17h00, du lundi au vendredi.  Toutes les heures exclues des heures d'ouverture sont considérées comme des heures de fermeture. Vous pouvez cliquer sur **Sélectionner une 24/7** pour prendre toutes les heures d’activité. Si vous n’avez pas sélectionné l’option **Sélectionner une 24/7** , la page des **paramètres d’appel après heures** est utilisée pour configurer la gestion des appels après les heures d’activité pour le standard automatique.

![Capture d’écran de la page des heures de bureau](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

Par défaut, les heures d’activité sont définies comme du lundi au vendredi, 9:00 AM-5:00 pm. Sélectionnez l’option **effacer toutes les heures** pour désélectionner toutes les heures heures dans le planning. Lorsque vous sélectionnez **rétablir les valeurs par défaut**, les heures d’ouverture sont réinitialisées au lundi au vendredi, 9:00 am-5:00 pm.

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

Pour modifier les heures d'ouverture, mettez en surbrillance les heures d'ouverture que vous voulez définir à l'aide du calendrier. Le calendrier vous permet de sélectionner des heures d’ouverture par intervalle de 30 minutes, et les heures d’ouverture sélectionnées ici seront définies en fonction du fuseau horaire que vous avez défini dans la page **informations générales** . Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier. Vous pouvez définir plusieurs sauts dans les heures de bureau.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="business-hours-call-settings"></a>Paramètres d’appel d’heures d’activité

> [!TIP]
> Si vous utilisez un planning personnalisé d’heures de travail, vous devez également configurer le suivi des appels après les heures d’activité à l’aide de la page de **traitement des appels après** les heures d’appel, qui vous offre les mêmes options que les **paramètres d’appel d’heures de travail**.

Vous pouvez configurer des messages d’accueil, des invites et des menus que les personnes qui rejoignent le numéro de téléphone du standard automatique de votre organisation pourront entendre pendant les heures d’activité.

![Capture d’écran de la section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![d’accueil de la page de gestion des appels en heures d’activité](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

**Message d’accueil** Un message d’accueil d’heures d’entreprise est facultatif et **ne peut pas**être défini pour le message d’accueil. Dans le cas présent, l’appelant n’entendra aucun message ou message d’accueil avant que l’appel ne soit géré par l’une des actions que vous sélectionnez. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.

- **Aucun message d’accueil** Aucun message d’accueil ne sera lu lorsque les personnes appellent le numéro de téléphone du standard automatique.
- **Télécharger un fichier audio** Si vous choisissez cette fonction, enregistrez le message d’accueil, puis téléchargez votre fichier audio (au format. wav,. mp3 ou. WMA).
- **Taper un message d’accueil** Si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères). Par exemple, vous pouvez entrer «Bienvenue dans contoso. Votre appel est important pour nous. dans la **** zone les appelants entendent.

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

Vous pouvez sélectionner ce qu’il advient des appels en temps réel. Vous pouvez choisir l’une des actions suivantes:

- **** Se déconnecter Si vous sélectionnez cette option, l’appelant sera déconnecté après avoir écouté un message d’accueil d’heures d’affaires.
- **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
  - **Personne de la société** disposant d’une licence de **système téléphonique** activée pour les offres d’appels voix entreprise ou affectées dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour cela, sélectionnez une **personne dans la société** et configurez cette personne de sorte que les appels soient transférés directement à la boîte vocale.

    > [!Note]
    > Une **personne de la société** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server 2015 ou Lync Server 2013.

   - Un autre **standard automatique**

   Vous pouvez utiliser un standard automatique existant pour créer un deuxième niveau d’options de menu contenant un sous-menu. Il s’agit des standards automatiques imbriqués. Pour envoyer l’appel à un standard automatique imbriqué, sélectionnez une **personne dans la société** et attribuez un compte de ressource, qui est déjà associé à un standard automatique ou que vous voulez associer à un standard automatique une fois que vous avez créé ce standard automatique.

- Vous pouvez également utiliser les **options de menu lire** pour vous permettre de configurer une invite à lire.

* * *

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l’invite dans la zone **Définissez votre navigation pour** les appelants ou enregistrez un fichier audio et dites, par exemple: «pour les ventes, Say ou appuyer sur 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. **Taper un message d’accueil** Si vous avez choisi cette méthode, vous devez entrer le texte que le système devra lire (jusqu’à 1000 caractères). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).

* * *

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

**Configuration des options de menu** Il est possible d’ajouter ou de supprimer des options de menu à l’aide de boutons clés sur le clavier. Pour ajouter une option de menu, appuyez sur **+ affecter une touche de numérotation**. Une ligne d’options correspondante apparaît en dessous. Pour supprimer une option de menu, il vous suffit de cliquer à gauche de la touche correspondante dans le contrôle clavier et de cliquer sur l’icône de suppression située au-dessus. La ligne de mappage clé sera supprimée.

> [!TIP]
> Vous devrez mettre à jour le texte des invites de menus ou réenregistrer l’audio séparément lors de l’ajout à la suppression d’options, car il n’est pas exécuté automatiquement pour l’invite de menu existante.  
>
>Toutes les options de menu peuvent être ajoutées et supprimées dans n’importe quel ordre, et les mappages de clés ne doivent pas nécessairement être continus. Par exemple, il est possible de créer un menu avec les clés 0, 1 et 3 mappées à des options, tandis que la clé 2 n’est pas utilisée.

> [!NOTE]
> Les clés \* (répétition) et \# (retour) sont réservées par le système et ne peuvent pas être réaffectées. Si la reconnaissance vocale est activée, le fait d’appuyer sur * correspond à «répéter» et # correspond aux commandes vocales «retour».

Pour configurer vos options de menu, après avoir sélectionné la ou les touches de numérotation, vous devrez:

- Entrez la **commande vocale** de l’option. Il peut y avoir un maximum de 64 caractères et contenir plusieurs mots tels que «service clientèle» ou «opérations et raisons». Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne qui appelle pourra soit appuyez sur 3, par exemple « 3 », ou dire « Service clientèle » pour sélectionner l’option mappée à la clé 3.
- Sélectionner l’endroit où l’appel doit être envoyé si la touche correspondante est enfoncée ou si l’option est sélectionnée à l’aide de la reconnaissance vocale. L’appel peut être envoyé à :

  - **Opérateur** Si l’opérateur a déjà été configuré, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffecté à une autre clé. Si l’opérateur n’est pas défini sur n’importe quelle touche, alors la commande vocale « Opérateur » sera désactivée aussi.
  - **Une Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Voix de l'Entreprise ou affectée à un Plan d’appel dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.

    > [!Note]
    > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. 
    - Un autre **standard automatique**

       Vous pouvez utiliser un standard automatique existant pour créer un deuxième niveau d’options de menu contenant un sous-menu. Il s’agit des standards automatiques imbriqués. Pour envoyer l’appel à un standard automatique imbriqué, sélectionnez une **personne dans la société** et attribuez un compte de ressource, qui est déjà associé à un standard automatique ou que vous voulez associer à un standard automatique une fois que vous avez créé ce standard automatique.

        > [!Note]
        > Les **heures d’ouverture** de standards automatiques imbriqués (ou de second niveau) seront également utilisé, y compris pour les appels envoyés à partir d’autres standards automatiques qui ont été définis.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Icône du numéro 5 qui référence une légende dans la capture d’écran précédente](media/sfbcallout5.png)

**Numérotation par nom** Si vous choisissez cette option, les utilisateurs qui se connectent pour rechercher des personnes dans votre organisation doivent effectuer une recherche dans l’annuaire. Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**. Tout utilisateur en ligne disposant d'une licence **   Phone System**  ou de tout utilisateur hébergé sur site à l'aide de Skype Professionnel Server 2015 ou Lync Server 2013 peut être trouvé avec Composer par Nom.


* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="holiday-call-settings"></a>Paramètres des appels de vacances

Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

> [!TIP]
> Vous pouvez accéder à l’écran des **** > **jours fériés** de votre organisation pour créer des jours fériés ou vous pouvez les créer dans le cadre de la création d’un nouveau gestionnaire d’appels.

![Capture d’écran de la page des paramètres des appels de vacances](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

Si vous avez déjà créé d’autres standards automatiques, vous verrez peut-être une option que vous pouvez utiliser ou modifier dans ce que vous avez besoin de cette liste. Si ce n’est pas le cas, vous devez créer un nouveau gestionnaire d’appels.

Pour ajouter un nouveau gestionnaire d’appels, cliquez sur **+ nouveau gestionnaire d’appels**.

* * *

![Capture d’écran montrant l’ajout d’un nouveau gestionnaire d’appels](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

Dans la nouvelle fenêtre, entrez un nom pour votre nouveau gestionnaire d’appels dans la partie supérieure de l’écran.

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

Si le nom de votre vacances existe déjà dans la liste déroulante **vacances** , vous pouvez l’utiliser. Si vous n’avez pas encore le nom du jour férié dont vous avez besoin, sélectionnez **créer un jour férié** dans la liste déroulante et attribuez un nom et une date pour le nouveau jour férié dans l’écran nouveau qui s’affiche. Cliquez sur **Enregistrer** lorsque vous êtes prêt.

Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être unique pour le même standard automatique. Par exemple, vous ne pouvez pas de jours fériés nommés « Actiondegrâce » dans le même standard automatique.

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

**Message d’accueil** Le message d’accueil est facultatif et ne peut **pas**être défini pour le message d’accueil. Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.

- **Aucun message d’accueil** Aucun message d’accueil ne sera lu lorsque les personnes appellent le numéro de téléphone du standard automatique.
- **Télécharger un fichier audio** Si vous choisissez cette fonction, enregistrez le message d’accueil du jour férié, puis chargez votre fichier audio (au format. wav,. mp3 ou. WMA).
- **Taper un message d’accueil** Si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères). Par exemple, vous pouvez entrer « bonne année ! Nos bureaux sont actuellement fermés. dans la boîte de dialogue **taper un message d’accueil** .

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

**Actions** Vous pouvez sélectionner ce qu’il advient des appels à ce jour. Vous pouvez choisir parmi les options suivantes :

- **Se déconnecter** La personne qui appel sera déconnectée après avoir entendu le message d’accueil du congé.
- **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
  - Une**  Personne de votre société**  disposant  d'une licence de ** Système téléphonique**  qui est activée pour Voix de l'Enterprise ou de plans d'appels associés dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour cela, sélectionnez une **personne au sein de votre entreprise**et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.

    > [!Note]
    > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. 

  - Une **file d’attente d’appels** pour transférer l’appel vers une file d’attente d’appels que vous avez configurée.
  - Un autre **standard automatique**pour créer un deuxième niveau d’options de menu contenant un sous-menu. Il s’agit des standards automatiques imbriqués.

    > [!Note]
    > Par défaut, tous les appels arrivant pendant une période de congé sont définies pour déconnecter la session après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.

#### <a name="select-dial-scope-page"></a>Page de sélection de la portée de la numérotation

Dans cette page, vous pouvez configurer les utilisateurs de votre organisation qui seront répertoriés dans votre annuaire et disponibles pour le numérotation par nom lorsqu’une personne appelle votre organisation.

![Capture d’écran montrant la page de portée de numérotation](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Icône du numéro 1, qui référence une légende dans la capture d'](media/sfbcallout1.png) écran précédente à l’aide de l’option **inclure** , vous avez deux options:

- **Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire. Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , ainsi que les utilisateurs hébergés sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013 qui ont des Plans d’appel dans Office 365, apparaîtront.
- **Groupe d’utilisateurs personnalisés** Si vous utilisez cette option, vous pouvez rechercher un groupe Office 365, une liste de distribution ou un groupe de sécurité qui a été créé au sein de votre organisation et les personnes ajoutées à ce groupe Office 365, liste de distribution ou groupe de sécurité qui sont des **utilisateurs en ligne avec un Licence du système téléphonique** ou hébergé sur site avec Skype entreprise Server 2015 ou Lync Server 2013. Vous pouvez ajouter plusieurs groupes 365 Office, des listes de distribution et des groupes de sécurité.

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

L’option **exclure** présente deux choix:

- **Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire.
- **Groupe d’utilisateurs personnalisés** Si vous utilisez cette option, vous pouvez rechercher un groupe, une liste de distribution ou un groupe de sécurité Office 365 qui a été créé au sein de votre organisation, et tous les participants ajoutés à ce groupe Office 365, liste de distribution ou groupes de sécurité seront exclus de la recherche dans l’annuaire. Vous pouvez ajouter plusieurs groupes 365 Office, des listes de distribution et des groupes de sécurité.

> [!NOTE]
> L’utilisation de la numérotation par nom avec la reconnaissance vocale peut prendre jusqu’à 36 heures pour qu’un nouveau utilisateur puisse avoir accès à son nom dans l’annuaire lorsque quelqu’un utilise la numérotation par nom.

Après avoir entré tous les champs requis et configuré l’ensemble des menus et options de traitement des appels, cliquez sur **valider**.

## <a name="editing-and-testing-auto-attendants"></a>Modification et test de standards automatiques

Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**. Vous pourrez ainsi voir rapidement certaines des options que vous avez configurées, y compris le nom, le numéro de téléphone, la langue et le statut.

Si vous voulez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis dans le volet action, cliquez sur **modifier**.

Vous pouvez également effectuer un test rapide de votre standard automatique à l’aide du bouton **test** dans le volet action.

## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.

### <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.

- [Nouveau-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [Nouveau-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [Nouveau-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [Nouveau-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [Nouvelle CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [Nouvelle CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [Nouvelle CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [Nouveau-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Importation-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [Nouveau-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Office 365 et Microsoft teams à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Voir aussi

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtention de numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Nouvelle CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)

[Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)  
