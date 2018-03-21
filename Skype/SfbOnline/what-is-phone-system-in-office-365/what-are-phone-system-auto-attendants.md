---
title: "Que sont les surveillances du système téléphonique ?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Découvrez les surveillances automatiques le système téléphonique (PBX nuage) et comment les utiliser. "
ms.openlocfilehash: 0c2478be3256d63a80263f70a1a70e6f2eaef3b3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="what-are-phone-system-auto-attendants"></a>Que sont les surveillances du système téléphonique ?

Système de téléphone dans Office 365 surveillances peuvent servir à créer un système de menus de votre organisation qui permet aux appelants d’internes et externes passent par un système de menus de localiser et de placer ou de transférer des appels vers les utilisateurs de la société ou les départements de votre organisation.
  
Lorsque les utilisateurs effectuent un appel, une série d'invites vocales les aident à passer un appel, ou à rechercher une personne de votre organisation pour l'appeler. Un standard automatique est une série d’invites vocales ou un fichier audio que les appelants entendront un opérateur humain lorsqu’ils appellent une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale. 
  
Pour configurer un standard automatique pour le système de téléphone dans Office 365, consultez [configurer une surveillance automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
  
Une surveillance automatique de système téléphonique présente les caractéristiques suivantes :
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
    
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
    
- Il fournit la recherche dans l’annuaire qui permet aux utilisateurs qui passent des appels dans pour rechercher le répertoire de l’organisation pour un nom.
    
- Permet à une personne qui appelle atteindre ou laisser un message à une personne de votre organisation.
    
## <a name="getting-started"></a>Mise en route

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :
  
- Une licence Enterprise E3 et **Système téléphonique** ou une licence Enterprise E5, votre organisation doit avoir (au minimum). Le nombre de licences d’utilisateur **Système téléphonique** qui sont affectés des impacts sur le nombre de service des numéros est disponible pour être utilisés pour les standards automatiques. Le nombre de surveillances automatiques que vous pouvez avoir est dépendant sur les licences de **Système téléphonique** et **Les conférences Audio** numériques qui vous sont affectées dans votre organisation. Pour en savoir plus sur les licences, consultez [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels à un opérateur ou une option de menu est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Voix Entreprise ou de leur attribuer des Plans d’appel. Reportez-vous à la section[Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros de service gratuit pour votre surveillances automatiques, vous devez configurer les crédits de Communications. Pour ce faire, reportez-vous à la section [que sont les crédits de Communications ?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) et [configurer les crédits de Communications pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
## <a name="feature-overview"></a>Présentation de la fonctionnalité

### <a name="dial-by-name"></a>Numérotation par nom

La Numérotation par nom est une fonction d'un standard automatique connue comme recherche dans l'annuaire. Il permet les personnes qui appellent votre automatique du service de surveillance permet d’entrer un nom complet ou partiel à rechercher le répertoire de la société, recherchez la personne et ont ensuite de transférer l’appel vers les voix (reconnaissance vocale) ou à leur clavier de téléphone (DTMF). Si vous avez Skype pour les utilisateurs professionnels en ligne, **ils ne sont pas tenus d’avoir un numéro de téléphone ou Plans d’appel de leur avez affecté aucune, mais ils doivent disposer d’une licence de système téléphonique** pour les rendre accessibles lorsqu’ils effectuent une recherche à l’aide de l’accès par nom. Accès par nom de sera encore en mesure de rechercher et de transférer les appels Skype pour des utilisateurs professionnels en ligne qui sont hébergés dans différents pays ou régions pour les multinationales.
  
> [!CAUTION]
> Les déploiements sur site des utilisateurs de Lync Server 2010 n’apparaît pas dans le répertoire lorsqu’une personne recherche les. 
  
### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’existe aucune limite sur la taille de Active Directory pour lequel l’accès par nom est pris en charge lors de l’utilisation du pavé numérique du téléphone pour effectuer une recherche partielle ou totale des noms (FirstName LastName et également nom + prénom). Toutefois, la taille de liste maximale pour le nom qu’une surveillance automatique unique peut prendre en charge à l’aide de la reconnaissance du nom avec la reconnaissance vocale est de 80 000 utilisateurs.
  
||||
|:-----|:-----|:-----|
|**Type d'entrée** <br/> |**Format de recherche** <br/> |**Nombre maximal d'utilisateurs dans une organisation** <br/> |
|DTMF (entrée de clavier de téléphone)  <br/> |Partiel  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |Aucune limite stricte  <br/> |
|Voix (entrée vocale)  <br/> |Prénom  <br/> Nom  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |80 000 utilisateurs  <br/> |
   
> [!NOTE]
> Si vous utilisez une connexion par nom avec la voix de reconnaissance, mais Active Directory de votre organisation est supérieure à 80 000 utilisateurs et vous n’avez pas limité la portée de l’accès à distance par un nom à l’aide de la fonctionnalité d’accès à portée, à distance par nom continuera à fonctionner pour vos appelants à l’aide d’un clavier de téléphone , et les entrées vocales sera disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Personnes se connectant pouvez utiliser numérotation par nom d’atteindre des utilisateurs en indiquant soit le nom complet ou partiel de la personne qu’il tente d’atteindre. La bonne chose est qu’il existe différents formats qui peuvent être utilisés lorsque le nom est entré.
  
Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsqu'ils saisissent le nom, ils seront invités à terminer leur entrée de clavier par la touche # (dièse). Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|||||
|:-----|:-----|:-----|:-----|
|**Format de nom** <br/> |**Type de recherche** <br/> |**Exemple** <br/> |**Résultat de recherche** <br/> |
|Prénom + nom  <br/> |Complet  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Nom + prénom  <br/> |Complet  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Prénom  <br/> |Complet  <br/> |Amos#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
|Nom  <br/> |Complet  <br/> |Marble#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble  <br/> |
|Prénom ou nom  <br/> |Partiel  <br/> |Mar#  <br/> |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus  <br/> |
|Prénom + nom  <br/> |Partiel  <br/> |Mar0Amos#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
|Nom + prénom  <br/> |Partiel  <br/> |Mar0Am#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
   
Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne sera demandée pour utiliser la touche dièse (#), tandis que la touche zéro (0) est utilisée pour un espace de noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|||
|:-----|:-----|
|**Caractère spécial du clavier téléphonique** <br/> |**Signification** <br/> |
|# (touche dièse)  <br/> |Caractère de fin de saisie d'un nom  <br/> |
|0 (zéro)  <br/> |Espace entre les noms  <br/> |
|* (touche étoile)  <br/> |Répétition de la liste de correspondances de noms  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Personnes peuvent rechercher d’autres utilisateurs de leur entreprise à l’aide de la voix (reconnaissance vocale). Ils peuvent également atteindre n’importe qui dans Active Directory la société en prononçant le nom de la personne qu’ils tentent de localiser. À l’aide d’entrées vocales peut reconnaître les noms dans différents formats, y compris les FirstName, LastName, FirstName LastName, ou nom + prénom.
  
Lorsque vous activez la reconnaissance vocale pour la surveillance automatique, entrée de clavier de téléphone (DTMF) ne sont pas désactivée, les deux types d’entrée peuvent être utilisée. Entrée de clavier de téléphone ne peut pas être désactivée et peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme avec l'entrée de clavier téléphonique, si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les appelants peuvent prononcer les noms dans les formats suivants :
  
|||||
|:-----|:-----|:-----|:-----|
|**Nom avec la voix** <br/> |**Type de recherche** <br/> |**Exemple** <br/> |**Résultat de recherche** <br/> |
|Prénom + nom  <br/> |Complet  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Nom + prénom  <br/> |Complet  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Prénom  <br/> |Complet  <br/> |Amos  <br/> |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones  <br/> |
|Nom  <br/> |Complet  <br/> |Marble  <br/> |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble  <br/> |
   
> [!NOTE]
> Il peut prendre jusqu'à 36 heures pour un nouvel utilisateur pour que leur nom répertorié dans l’annuaire pour l’accès par nom avec la reconnaissance vocale. 
  
### <a name="language-support"></a>Prise en charge des langues

Les langues suivantes sont disponibles pour la synthèse vocale :
  
||||
|:-----|:-----|:-----|
|Arabe (EG)  <br/> |Anglais (NZ)  <br/> |Coréen (KO)  <br/> |
|Chinois (HK)  <br/> |Anglais (Royaume-Uni)  <br/> |Norvégien (NO)  <br/> |
|Chinois (TW)  <br/> |Anglais (É.U.)  <br/> |Polonais (PL)  <br/> |
|Chinois (ZH)  <br/> |Finnois (FI)  <br/> |Portugais (BR)  <br/> |
|Danois (DA)  <br/> |Français (CA)  <br/> |Portugais (PT)  <br/> |
|Néerlandais (NL)  <br/> |Français (FR)  <br/> |Russe (RU)  <br/> |
|Anglais (AU)  <br/> |Allemand (DE)  <br/> |Espagnol (ES)  <br/> |
|Anglais (CA)  <br/> |Italien (IT)  <br/> |Espagnol (MX)  <br/> |
|Anglais (IN)  <br/> |Japonais (JP)  <br/> |Suédois (SV)  <br/> |
   
La reconnaissance vocale pour les standards automatiques est disponible pour les langues suivantes :
  
|||
|:-----|:-----|
|Chinois (ZH)  <br/> |Français (FR)  <br/> |
|Anglais (AU)  <br/> |Allemand (DE)  <br/> |
|Anglais (CA)  <br/> |Italien (IT)  <br/> |
|Anglais (IN)  <br/> |Japonais (JP)  <br/> |
|Anglais (Royaume-Uni)  <br/> |Portugais (BR)  <br/> |
|Anglais (É.U.)  <br/> |Espagnol (ES)  <br/> |
|Français (CA)  <br/> |Espagnol (MX)  <br/> |
   
Les commandes vocales suivantes sont disponibles dans les quatorze (14) langues prises en charge par la reconnaissance vocale :
  
|||
|:-----|:-----|
|**Commande vocale** <br/> |**Signification** <br/> |
|Oui  <br/> |Oui correspond à appuyer sur 1 pour indiquer Oui.  <br/> |
|Non  <br/> |Non correspond à appuyer sur 2 pour indiquer Non.  <br/> |
|Répéter  <br/> |Répète la liste des options - correspond à appuyer sur * pour répéter la liste des options.  <br/> |
|Opérateur  <br/> |Contacter un opérateur - correspond à appuyer sur 0 pour « Opérateur ».  <br/> |
|Menu principal  <br/> |Dirige l'appelant vers le menu principal du standard automatique.  <br/> |
|Zéro  <br/> |Correspond à appuyer sur 0 (par défaut, identique à « Opérateur »).  <br/> |
|Un  <br/> |Correspond à appuyer sur 1.  <br/> |
|Deux  <br/> |Correspond à appuyer sur 2.  <br/> |
|Trois  <br/> |Correspond à appuyer sur 3.  <br/> |
|Quatre  <br/> |Correspond à appuyer sur 4.  <br/> |
|Cinq  <br/> |Correspond à appuyer sur 5.  <br/> |
|Six  <br/> |Correspond à appuyer sur 6.  <br/> |
|Sept  <br/> |Correspond à appuyer sur 7.  <br/> |
|Huit  <br/> |Correspond à appuyer sur 8.  <br/> |
|Neuf  <br/> |Correspond à appuyer sur 9.  <br/> |
   
### <a name="using-the-operator-option"></a>Utilisation de l'option opérateur

L'utilisation de l'opérateur d'un standard automatique est un paramètre facultatif qui permet à l'appelant de contacter une personne.
  
La touche 0 et la commande vocale « Opérateur » (dans toutes les langues prises en charge par la reconnaissance vocale) sont affectées à l'opérateur par défaut.
  
> [!NOTE]
> Vous pouvez définir le bouton qui est basculé vers une clé différente pour l' **opérateur** à l’aide des **Options de Menu**. 
  
Vous pouvez définir l'opérateur comme suit :
  
- Un Skype pour Business Online utilisateur qui dispose d’un **Système téléphonique** de licence qui est activé de Voix Entreprise ou a les Plans d’appel attribuée. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé comme un opérateur. 
  
- Un autre standard automatique configuré dans votre organisation
    
- Une file d'attente existante configurée dans votre organisation. Pour plus d’informations sur les files d’attente de l’appel, consultez [créer une file d’attente des appels système téléphonique](create-a-phone-system-call-queue.md).
    
### <a name="business-hours-and-call-handling"></a>Heures d'ouverture et traitement des appels

Les heures d'ouverture sont définies sur chaque standard automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures peuvent être définies avec des sauts dans le temps au cours de la journée et toutes les heures qui ne sont pas définis comme les heures de bureau sont considérés comme en continu. Vous pouvez définir différentes options de gestion des appels entrantes et les salutations différentes (qui sont facultatifs), et les deux peuvent être définies pour les heures de bureau et en continu.
  
Chaque surveillance automatique a gestion d’appel les options qui peuvent être définies :
  
- Vous pouvez définir la déconnexion de l'appel juste après le message d'accueil.
    
- Vous pouvez également :
    
  - Redirection d’appel vers un Skype pour Business Online utilisateur qui dispose d’une licence de **Système téléphonique** est activée en Voix Entreprise ou a les Plans d’appel attribuée. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge. 
  
  - Redirection d’appel vers une file d’attente d’appel. Pour plus d’informations sur les files d’attente de l’appel, consultez [créer une file d’attente des appels système téléphonique](create-a-phone-system-call-queue.md).
    
  - Redirection d’appel vers un autre standard automatique que vous avez configurées.
    
- Créer des options de menu et activer une invite de menu pour l'appelant. Par exemple : « Appuyez sur 1 pour contacter le département des ventes, appuyez sur 2 pour contacter le département des services. Pour contacter l'opérateur, appuyez sur 0 à tout moment. »
    
### <a name="menu-options"></a>Options de menu

Surveillances automatiques de système téléphonique vous permettent de créer des invites de menu (« appuyez sur 1 pour les ventes, appuyez sur 2 pour les Services ») et de définir les options de menu à acheminer les appels en fonction de ce que l’utilisateur sélectionne. La configuration des options de menu d'un standard automatique permet à une organisation de fournir une assistance interactive pour orienter rapidement l'appelant vers sa destination, sans recourir à un opérateur humain pour la gestion des appels entrants. Invites de menu peuvent être créés à l’aide de conversion vocale du texte (généré par le système à l’écran) ou en téléchargeant un fichier audio qui a été enregistré. La reconnaissance vocale utilise des commandes vocales pour naviguer en mode mains libres, mais les appelants peuvent également utiliser leur clavier téléphonique pour parcourir les menus.
  
Touches 0 à 9 peuvent avoir sur **Les Options de Menu** dans un standard automatique à l’aide de la Skype pour le centre d’administration Business. Plusieurs ensembles d'options de menu peuvent être créés pour les heures d'ouverture et de fermeture et vous pouvez activer ou désactiver la fonction Numérotation par nom dans les **Options de menus**. Les touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur, mappé vers la touche 0 par défaut. Toutefois, il peut être réaffecté à n’importe quelle autre touche ou retiré du menu.
    
- Une file d’attente de l’appel.
    
- Un autre standard automatique. Menus multi-niveaux permet de configurer en pointant une **Option de Menu** dans la surveillance un automatique à un autre standard automatique avec son propre jeu d’Options de Menu, qui est appelé une surveillance automatique « imbriquées ».
    
- Un Skype pour Business Online utilisateur qui dispose d’un **Système téléphonique** de licence qui est activé de Voix Entreprise ou a les Plans d’appel attribuée. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé dans les **Options de Menu**. 
  
Le nom de chaque option de menu devient un mot clé de la reconnaissance vocale si la reconnaissance vocale n’a pas été activée. Par exemple, appelants peuvent dire "Un" pour sélectionner l’option de menu mappée à la clé 1, ou ils peuvent dire « Ventes » pour sélectionner la même option de menu nommée « Sales ».
  
Pour configurer un standard automatique et les options de menu, consultez [configurer une surveillance automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Obtention de numéros de service pour un standard automatique

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Une fois que vous obtenez le numéro payant ou les numéros de téléphone de service gratuit, ils apparaîtront dans le **Skype pour le centre d’administration Business** > **vocale** > **les numéros de téléphone**et la volonté de **type nombre** répertorié comme **Service - numéro gratuit **. Pour obtenir vos numéros de service, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](getting-service-phone-numbers.md) ou, si vous souhaitez de transfert et le numéro de service existant, consultez le [transfert vers Office 365, les numéros de téléphone](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous résidez hors des États-Unis, vous ne pouvez pas utiliser le Skype pour Business admin center pour obtenir les numéros de service. Allez [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modification de l’ID de l’utilisateur appelant pour être le numéro de téléphone d’une file d’attente appel

Vous pouvez protéger l’identité d’un utilisateur en modifiant à la place de leur ID de l’appelant pour les appels sortants d’une file d’attente de l’appel en créant une stratégie à l’aide de l’applet de commande **New-CallingLineIdentity** .
  
Pour ce faire, exécutez la commande :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez la commande :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon de modifier les paramètres d’ID de l’appelant dans votre organisation, [ID de l’appelant utilisation dans votre organisation](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)