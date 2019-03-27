---
title: Configurer les standards automatiques du système téléphonique
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez comment configurer et tester les standards automatiques de système téléphonique (PBX nuage) pour efficace gestion des appels pour votre organisation.
ms.openlocfilehash: 5071b3c26809e56df4cdd922ed1df2e67fc9481c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873478"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurer les standards automatiques du système téléphonique

Standards automatiques permettent aux personnes qui appellent votre organisation et accédez à les atteindre le bon service, appelez la file d’attente, la personne ou l’opérateur un système de menus. Vous pouvez créer un standard automatique pour votre organisation à l’aide du centre d’administration Microsoft Teams. Pour créer un nouveau standard automatique, accédez à la **voix** dans le volet de navigation gauche et sélectionnez **standards automatiques** > **Nouveau**.

Si vous souhaitez en savoir plus sur les standards automatiques, voir [Quelles sont les standards automatiques de système téléphonique ?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Cet article s’applique à Microsoft Teams et Skype pour Business Online.

## <a name="step-1---get-started"></a>Étape 1 : mise en route

- Avant de pouvoir créer et configurer votre standards automatiques, si le standard automatique aura un numéro de téléphone (et de second niveau invite ou imbriquée sera de standards automatiques ne nécessitent un numéro de téléphone) que vous devrez obtenir ou transférer votre appel payant existant ou un service gratuit numéros . Une fois que vous obtenez les numéros gratuits service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > page de**numéros de téléphone** . Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json), ou si vous souhaitez transférer et le numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md). **User (subscriber)** numbers can't be assigned to auto attendants. Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service ; Accédez [ici](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    > [!CAUTION]
    > Pour obtenir et utiliser les numéros de téléphone, vous devez configurer les crédits de Communications. Pour faire cela, consultez [Quelles sont les Communications crédits ?](what-are-communications-credits.md) et [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les standards automatiques. Les numéros des standards automatiques que vous pouvez avoir dépend de licences numéros **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour plus d’informations sur les licences, voir [Skype pour la licence de module complémentaire Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) ou [équipes Microsoft licensing de module complémentaire](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). .

    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Enterprise Voice ou de leur attribuer des Plans de l’appel dans Office 365. Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Étape 2 : création d'un standard automatique

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer au standard automatique.

### <a name="using-the-microsoft-teams-admin-center"></a>À l’aide du centre d’administration Microsoft Teams

Dans le **Centre d’administration équipes Microsoft**, cliquez sur **voix** > **standards automatiques**, puis cliquez sur **+ Nouveau**:

#### <a name="general-info-page"></a>Page Infos générales

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Numéro 1](media/sfbcallout1.png)

**Nom** Entrez un nom d’affichage de la description pour le standard automatique. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Il sera répertorié dans la colonne **Nom** de l'onglet **Standards automatiques**.

* * *

![Numéro 2](media/sfbcallout2.png)

**Compte de ressource** Cliquez sur ce bouton pour sélectionner un ou plusieurs comptes de ressources pour vous connecter à votre nouveau standard automatique. Tous les standards automatiques doit être un compte de ressource. Un compte de ressource peut avoir un numéro de téléphone associé au compte, mais il risque de ne pas. Un standard automatique de niveau supérieur serait certainement aurait un compte de ressource avec un numéro de téléphone attribuée, mais un standard automatique secondaire (utilisé comme un menu de niveau 2 le standard automatique de niveau premier se connecte à) facilement peut-être pas affecté à un numéro de téléphone son compte de ressource.

* * *

![Nombre 3](media/sfbcallout3.png)

**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.

* * *

![Numéro 4](media/sfbcallout4.png)

**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées. La langue que vous définissez ici est la langue que le standard automatique utilisera pour interagir avec des personnes qui appellent ce standard automatique et toutes les invites système seront énoncées dans cette langue.

* * *

!["Nombre 5"](media/sfbcallout5.png)

**Opérateur** Cette option est facultative ne doit pas nécessairement être définie pour le standard automatique. Toutefois, vous pouvez définir l’option **opérateur** des personnes appellent pour sortir les menus de parler à une personne pour leur permettre de pouvoir.

La touche 0 est automatiquement affectée à l'option Opérateur.

Si vous configurer ce paramètre, vous devez également indiquer aux personnes qui appellent que ceci est une option disponible dans le **menu options d’édition** dans la page **Gestion des appels en heures** . Si vous définissez un opérateur pour le standard automatique, vous devrez entrer le texte du message correspondant dans la zone **appelants entendront** ou modifier votre fichier audio pour inclure cette option. Par exemple, « pour l’opérateur, appuyez sur zéro. »

L'opérateur peut être défini comme suit :

- **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365.

     > [!Note]
     > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.

- Un **appel de file d’attente** que vous avez configurées.
- Vous pouvez la configurer de manière qu'une personne appelant soit renvoyée sur la messagerie. Pour ce faire, sélectionnez la **personne de votre société** et définir les appels de cette personne à transférer directement vers la messagerie vocale.

* * *

![Numéro 6](media/sfbcallout6.png)

**Activer les entrées vocales** La reconnaissance vocale est disponible si cette option est sélectionnée. Personnes qui appellent dans peuvent utiliser entrée vocale dans la [langue définie](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Vous pouvez désactiver la reconnaissance vocale en définissant la désactiver si vous souhaitez uniquement permettent aux utilisateurs à utiliser leur clavier du téléphone.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="business-hours-page"></a>Page heures

Par défaut, les heures ouvrées sont définies à 9 h 00 à 17 h 00, du lundi au vendredi.  Toutes les heures exclues des heures d'ouverture sont considérées comme des heures de fermeture. Vous pouvez cliquer sur **Sélectionner 24 x 7** pour toutes les heures d’heures. Sauf si vous sélectionnez l’option **Sélectionner 24 x 7** , la page **d’après les paramètres des appels heures** sera utilisée pour configurer la gestion des appels pour après les heures d’ouverture pour le standard automatique.

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Numéro 1](media/sfbcallout1.png)

Par défaut, les heures ouvrées sont définies à lundi au vendredi, de 9 h 00-17 h 00. L’option **désactiver toutes les heures** pour désélectionner toutes les heures d’heures de la planification. Lorsque vous sélectionnez **Rétablir par défaut**, les heures de bureau seront réinitialisées à lundi au vendredi, de 9 h 00-17 h 00.

* * *

![Numéro 2](media/sfbcallout2.png)

Pour modifier les heures d'ouverture, mettez en surbrillance les heures d'ouverture que vous voulez définir à l'aide du calendrier. Le calendrier permet de sélectionner les heures d’ouverture de 30 minutes, et les heures ouvrées que vous sélectionnez ici sera définies en fonction du fuseau horaire que vous avez définie dans la page **informations générales** . Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier. Vous pouvez définir plusieurs sauts dans les heures de bureau.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="business-hours-call-settings"></a>Paramètres des heures d’appels

> [!TIP]
> Si vous utilisez un calendrier des heures de travail personnalisées, vous devez également configurer un traitement après les heures de bureau à l’aide de la page **après que les heures de gestion des appels** , qui vous donne les mêmes options que les **Paramètres des heures d’appels**pour l’appel.

Vous pouvez configurer le message d’accueil et invites menus que les personnes appel de numéro de téléphone du standard automatique de votre organisation entendra pendant les heures ouvrées.

![Les heures de bureau de gestion des appels. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Heures suite des appels.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Numéro 1](media/sfbcallout1.png)

**Message d’accueil** Un accueil pendant les heures est facultatif et peut être définie sur **aucun message d’accueil**. Dans ce cas, l’appelant n’entendra aucun message ou un message d’accueil avant l’appel est traité par l’une des actions que vous sélectionnez. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.

- **Aucun message d’accueil** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.
- **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil et puis téléchargez votre fichier audio (au format .wav, .mp3 ou .wma).
- **Type d’un message de bienvenue** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum). Par exemple, vous pouvez entrer « Bienvenue dans Contoso. Votre appel est important pour nous. dans la zone **appelants** .

* * *

![Numéro 2](media/sfbcallout2.png)

Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant les heures ouvrées. Vous pouvez choisir parmi les actions suivantes :

- **Se déconnecter** Si vous l’activez, la personne l’appel sera déconnectée après audition un accueil pendant les heures.
- **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
  - **Personne dans la société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée des Plans de l’appel dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez la **personne dans la société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.

    > [!Note]
    > **Personne dans la société** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.

   - Un autre **standard automatique**

   Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués. Pour envoyer l’appel vers un standard automatique imbriquées, sélectionnez la **personne dans la société** et affecter un compte de ressource, une ayant déjà un standard automatique associée ou que vous associez à un standard automatique une fois que vous avez terminé la création de ce standard automatique.

- **Lire les options de menu** peut également servir à vous permettent de définir une invite désiré.

* * *

![Nombre 3](media/sfbcallout3.png)

**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l’invite dans la zone **définir votre navigation de menu pour les appelants** ou enregistrer un fichier audio et le dites, par exemple : « pour les ventes, dites ou appuyez sur ou dites 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. **Type d’un message de bienvenue** Si vous choisissez cette option, vous devez entrer le texte que vous souhaitez que le système pour lire (1000 caractères maximum). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).

* * *

![Numéro 4](media/sfbcallout4.png)

**Configuration des options de menu** Options de menu à l’aide de boutons clés du pavé numérique peuvent être ajoutées ou supprimées. Pour ajouter une option de menu, appuyez sur la touche **+ affecter une touche d’accès à distance**. Une ligne des options s’affiche ci-dessous. Pour supprimer une option de menu, cliquez à gauche de la clé correspondante sur le contrôle pavé numérique simplement et cliquez sur l’icône de suppression ci-dessus. La ligne de mappage clé sera supprimée.

> [!TIP]
> Vous devrez mettre à jour le texte des invites de menu ou réenregistrer l’audio séparément lors de l’ajout à la suppression des options, car elle ne s’effectue automatiquement de l’invite de menu existants.  
>
>Une option de menu peut être ajoutée et supprimée dans n’importe quel ordre, et les mappages de clés ne doivent pas être continue. Il est possible, par exemple, pour créer un menu avec les touches 0, 1 et 3 mappés aux options, tandis que la touche 2 n’est pas utilisée.

> [!NOTE]
> Les clés de \* (répétition) et \# (retour) sont réservées par le système et ne peut pas être réaffectés. Si la reconnaissance vocale est activée, en appuyant sur * correspond à « Répéter » et # correspond avec les commandes vocales « Nouveau ».

Pour configurer vos options de menu, une fois que vous sélectionnez les touches de numérotation, vous devez :

- Entrez la **commande vocale** de l’option. Il peut contenir jusqu'à 64 caractères et peut contenir plusieurs mots comme « Service clientèle » ou « opérations et motifs ». Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne qui appelle pourra soit appuyez sur 3, par exemple « 3 », ou dire « Service clientèle » pour sélectionner l’option mappée à la clé 3.
- Sélectionnez où l’appel doit être envoyé si la clé correspondante est activée, ou l’option est sélectionnée à l’aide de la reconnaissance vocale. L’appel peut être envoyé à :

  - **Opérateur** Si l’opérateur a déjà été configuré, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffecté à une autre clé. Si l’opérateur n’est pas défini sur n’importe quelle touche, alors la commande vocale « Opérateur » sera désactivée aussi.
  - **Une Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Voix de l'Entreprise ou affectée à un Plan d’appel dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.

    > [!Note]
    > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.
    - Un autre **standard automatique**

       Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués. Pour envoyer l’appel vers un standard automatique imbriquées, sélectionnez la **personne dans la société** et affecter un compte de ressource, une ayant déjà un standard automatique associée ou que vous associez à un standard automatique une fois que vous avez terminé la création de ce standard automatique.

        > [!Note]
        > Les **heures d’ouverture** de standards automatiques imbriqués (ou de second niveau) seront également utilisé, y compris pour les appels envoyés à partir d’autres standards automatiques qui ont été définis.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

!["Nombre 5"](media/sfbcallout5.png)

**Numérotation par nom** Si vous choisissez cette option, vous activez des personnes appellent pour rechercher des personnes dans votre organisation à l’aide de la recherche dans l’annuaire. Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**. Tout utilisateur en ligne disposant d'une licence **   Phone System**  ou de tout utilisateur hébergé sur site à l'aide de Skype Professionnel Server 2015 ou Lync Server 2013 peut être trouvé avec Composer par Nom.

> [!WARNING]
> Les utilisateurs hébergés sur site à l’aide de Lync 2010 **ne sont pas joignables** avec numérotation par nom.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="holiday-call-settings"></a>Paramètres d’appel de congé

Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

> [!TIP]
> Vous pouvez passer le l’écran **paramètres à l’échelle de la société** > **congés** pour créer des congés, ou vous pouvez les créer dans le cadre de la création d’un nouveau gestionnaire d’appel.

![Définition des congés dans le standard automatique](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Numéro 1](media/sfbcallout1.png)

Si vous avez déjà créé les standards automatiques, vous pouvez voir une option, vous pouvez utiliser ou modifier dans ce que vous devez sur cette liste. Si ce n’est pas le cas, vous devez créer un nouveau gestionnaire d’appel.

Pour ajouter un nouveau gestionnaire d’appel, cliquez sur **+ nouveau gestionnaire d’appel**.

* * *

![Configuration de congés dans le standard automatique (suite)](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Numéro 1](media/sfbcallout1.png)

Dans la nouvelle fenêtre, entrez un nom pour votre nouveau gestionnaire d’appel dans la partie supérieure de l’écran.

![Numéro 2](media/sfbcallout2.png)

Si le nom de votre groupe de congés déjà existe dans la liste déroulante **période de congé** , vous pouvez l’utiliser. Si le nom du congé n’existe pas déjà, sélectionnez **Créer nouveau congé** dans la liste déroulante et attribuer un nom et une date pour le nouveau congé dans le nouvel écran qui s’affiche. Cliquez sur **Enregistrer** lorsque vous êtes prêt.

Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être unique pour le même standard automatique. Par exemple, vous ne pouvez pas de jours fériés nommés « Actiondegrâce » dans le même standard automatique.

![Nombre 3](media/sfbcallout3.png)

**Message d’accueil** Le message d’accueil est facultatif et peut être définie sur **aucun message d’accueil**. Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.

- **Aucun message d’accueil** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.
- **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil de congé et télécharger le fichier audio (au format .wav, .mp3 ou .wma)
- **Type d’un message de bienvenue** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum). Par exemple, vous pouvez entrer « bonne année ! Nos bureaux sont actuellement fermés. dans la zone **Tapez un message de bienvenue** .

![Numéro 4](media/sfbcallout4.png)

**Actions** Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant cette période de congé. Vous pouvez choisir parmi les options suivantes :

- **Se déconnecter** La personne qui appel sera déconnectée après avoir entendu le message d’accueil du congé.
- **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
  - Une**  Personne de votre société**  disposant  d'une licence de ** Système téléphonique**  qui est activée pour Voix de l'Enterprise ou de plans d'appels associés dans Office 365. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société**et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.

    > [!Note]
    > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.

  - Une **file d’attente d’appel** pour transférer l’appel vers une file d’attente appel existant que vous avez configurées.
  - Un autre **standard automatique**, pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués.

    > [!Note]
    > Par défaut, tous les appels arrivant pendant une période de congé sont définies pour déconnecter la session après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.

#### <a name="select-dial-scope-page"></a>Page de sélection de la portée de la numérotation

Dans cette page, vous pouvez configurer les utilisateurs de votre organisation seront répertoriés dans le répertoire et disponibles pour la numérotation par nom lorsqu’une personne qui appelle votre organisation.

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![N ° 1](media/sfbcallout1.png) à l’aide de l’option **inclure** , vous disposez de deux options :

- **Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire. Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , ainsi que les utilisateurs hébergés sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013 qui ont des Plans d’appel dans Office 365, apparaîtront.
- **Groupe d’utilisateurs personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation et les personnes ajouté à ce groupe dans Office 365, liste de distribution ou groupe de sécurité qui sont soit **utilisateurs en ligne avec un Licence de système téléphonique** ou hébergée sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité.

  > [!Caution]
  > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom.

* * *

![Numéro 2](media/sfbcallout2.png)

À l’aide de l’option **Exclure** , vous disposez de deux options :

- **Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire.
- **Groupe d’utilisateurs personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et tous les utilisateurs ajoutés à ce groupe d’Office 365, liste de distribution, ou groupes de sécurité seront exclus de la recherche dans l’annuaire. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité.

  > [!Caution]
  > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom.

> [!NOTE]
> Cela peut prendre jusqu'à 36 heures pour un nouvel utilisateur à leur nom apparaît dans le répertoire lorsqu’une personne utilise la numérotation par un nom pour la reconnaissance vocale.

Une fois que vous entrez tous les champs obligatoires et que vous définissez des menus et les options de gestion des appels, cliquez sur **Envoyer**.

## <a name="editing-and-testing-auto-attendants"></a>Modification et le test des standards automatiques

Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**. Cela vous permettra de voir rapidement les options que vous avez configuré, notamment le nom, numéro de téléphone, langue et le statut.

Si vous souhaitez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis cliquez sur **Modifier**dans le volet Actions.

Vous pouvez également rapidement placer un test d’appel pour le standard automatique en utilisant le bouton de **Test** dans le volet Actions.

## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.

### <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.

|||
|---  |---  |
| [Nouvelle CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx) | [Nouvelle CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx) |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx) | [Nouvelle CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx) |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx) | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx) | [Nouvelle CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx) |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx) | [Nouvelle CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx) |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Nouvelle CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx) |
| [Nouvelle CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) | [Nouvelle CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx) | [Nouvelle CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx) | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Nouvelle CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx) | |

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Rubriques connexes

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtention de numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Nouvelle CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Quels sont les standards automatiques du système téléphonique ?](what-are-phone-system-auto-attendants.md)

[Exemple de petite entreprise : configurer un standard automatique](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa
)  