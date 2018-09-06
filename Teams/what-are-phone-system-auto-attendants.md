---
title: Que sont les standards automatiques de système téléphonique ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez quelles sont les standards automatiques de système téléphonique (PBX en nuage) et comment les utiliser. '
ms.openlocfilehash: 31a9a9c7a292014cac01909274b7d5de1b640655
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23784781"
---
# <a name="what-are-phone-system-auto-attendants"></a>Que sont les standards automatiques de système téléphonique ?

Système téléphonique dans Office 365 standards automatiques peuvent servir à créer un système de menus pour votre organisation qui permet aux appelants internes et externes passent par un système de menus pour localiser et placer ou transférer des appels vers les utilisateurs de la société ou département au sein de votre organisation.
  
Lorsque les utilisateurs effectuent un appel, une série d'invites vocales les aident à passer un appel, ou à rechercher une personne de votre organisation pour l'appeler. Un standard automatique est une série d’invites vocales ou un fichier audio que les appelants entendront au lieu d’un opérateur humain quand ils appellent vers une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale. 
  
Pour configurer un standard automatique pour le système téléphonique dans Office 365, accédez à [configurer un standard automatique de système téléphonique](/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
Un standard automatique de système téléphonique comprend les fonctionnalités suivantes :
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
    
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
    
- Il fournit la recherche dans l’annuaire qui permet à des personnes appellent recherche dans le répertoire de l’organisation pour un nom.
    
- Il permet à une personne qui appelle l’appel ou laisser un message d’une personne dans votre organisation.
    
## <a name="getting-started"></a>Mise en route

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont affectés des impacts sur le numéro de service des numéros est disponible pour être utilisés pour les standards automatiques. Le nombre de standards automatiques que vous avez dépend des licences numéros **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour plus d’informations sur les licences, accédez [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Enterprise Voice ou de leur attribuer des Plans de l’appel. Voir[Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros gratuits service pour vos standards automatiques, vous devez configurer les crédits de Communications. Pour ce faire, consultez la rubrique [Quelles sont les Communications crédits ?](what-are-communications-credits.md) et [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
## <a name="feature-overview"></a>Présentation de la fonctionnalité

### <a name="dial-by-name"></a>Numérotation par nom

La Numérotation par nom est une fonction d'un standard automatique connue comme recherche dans l'annuaire. Elle permet les personnes qui appellent le standard automatique à permet d’entrer un nom complet ou partiel recherche dans le répertoire de la société, recherchez la personne et ont puis transférer l’appel vers les voix (reconnaissance vocale) ou leur clavier du téléphone (DTMF). Si vous avez Skype pour les utilisateurs professionnels en ligne, **n’est pas nécessaires de posséder un numéro de téléphone ou l’appel des Plans de leur sont assignées, mais ils doivent disposer d’une licence de système téléphonique** pour les rendre accessibles lorsqu’ils cherchent à l’aide de la numérotation par nom. Numérotation par nom pourront même rechercher et transférer des appels vers Skype pour les utilisateurs professionnels en ligne qui sont hébergées dans plusieurs pays ou régions pour les organisations multinationale.
  
> [!CAUTION]
> Déploiements locaux des utilisateurs de Lync Server 2010 n’apparaît pas dans le répertoire lorsqu’une personne recherche pour eux. 
  
### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’existe aucune limite la taille d’Active Directory pour lesquels la numérotation par nom est pris en charge lors de l’utilisation du clavier du téléphone pour rechercher les noms complet ou partiel (FirstName + LastName, également LastName et FirstName). Toutefois, la taille de liste maximale pour le nom qu’un standard automatique unique peut prendre en charge à l’aide de la reconnaissance de nom avec la voix est 80 000 utilisateurs.
  
||||
|:-----|:-----|:-----|
|**Type d'entrée** <br/> |**Format de recherche** <br/> |**Nombre maximal d'utilisateurs dans une organisation** <br/> |
|DTMF (entrée de clavier de téléphone)  <br/> |Partiel  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |Aucune limite stricte  <br/> |
|Voix (entrée vocale)  <br/> |Prénom  <br/> LastName  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |80 000 utilisateurs  <br/> |
   
> [!NOTE]
> Si vous utilisez la numérotation par un nom avec la voix de reconnaissance, mais Active Directory votre organisation est supérieure à 80 000 utilisateurs et vous n’avez pas limité à l’étendue de numérotation par un nom à l’aide de la fonctionnalité d’étendue de numérotation, numérotation par nom continuent de fonctionner pour vos interlocuteurs à l’aide d’un clavier de téléphone , et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Personnes appelant peuvent utiliser à distance par un nom d’atteindre des utilisateurs en spécifiant soit le nom complet ou partiel de la personne qu’il tente d’accéder. La bonne chose est qu’il existe différents formats qui peuvent être utilisés lorsque le nom est entré.
  
Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsqu'ils saisissent le nom, ils seront invités à terminer leur entrée de clavier par la touche # (dièse). Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|||||
|:-----|:-----|:-----|:-----|
|**Format de nom** <br/> |**Type de recherche** <br/> |**Exemple** <br/> |**Résultat de recherche** <br/> |
|Prénom + nom  <br/> |Complet  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Nom + prénom  <br/> |Complet  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Prénom  <br/> |Complet  <br/> |Amos#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
|LastName  <br/> |Complet  <br/> |Marble#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble  <br/> |
|Prénom ou nom  <br/> |Partiel  <br/> |Mar#  <br/> |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus  <br/> |
|Prénom + nom  <br/> |Partiel  <br/> |Mar0Amos#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
|Nom + prénom  <br/> |Partiel  <br/> |Mar0Am#  <br/> |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus  <br/> |
   
Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne devront utiliser la touche dièse (#), tandis que la touche zéro (0) est utilisée pour un espace de noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|||
|:-----|:-----|
|**Caractère spécial du clavier téléphonique** <br/> |**Signification** <br/> |
|# (touche dièse)  <br/> |Caractère de fin de saisie d'un nom  <br/> |
|0 (zéro)  <br/> |Espace entre les noms  <br/> |
|* (touche étoile)  <br/> |Répétition de la liste de correspondances de noms  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Personnes peuvent rechercher d’autres utilisateurs dans leur organisation à l’aide de la voix (reconnaissance vocale). Ils peuvent également joindre tout le monde dans Active Directory de l’entreprise en indiquant le nom de la personne, qu’ils vous recherchez. À l’aide d’entrées vocales peut reconnaître les noms dans différents formats, y compris FirstName, LastName, FirstName LastName, ou LastName + FirstName.
  
Lorsque vous activez la reconnaissance vocale pour un standard automatique, entrée de clavier de téléphone (DTMF) n’est pas désactivée, les deux types d’entrée peuvent être utilisée. Entrée clavier de téléphone ne peut pas être désactivée et peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme avec l'entrée de clavier téléphonique, si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les appelants peuvent prononcer les noms dans les formats suivants :
  
|||||
|:-----|:-----|:-----|:-----|
|**Nom de la reconnaissance vocale** <br/> |**Type de recherche** <br/> |**Exemple** <br/> |**Résultat de recherche** <br/> |
|Prénom + nom  <br/> |Complet  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Nom + prénom  <br/> |Complet  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Prénom  <br/> |Complet  <br/> |Amos  <br/> |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones  <br/> |
|LastName  <br/> |Complet  <br/> |Marble  <br/> |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble  <br/> |
   
> [!NOTE]
> Cela peut prendre jusqu'à 36 heures pour un nouvel utilisateur à leur nom apparaît dans le répertoire de numérotation par un nom pour la reconnaissance vocale. 
  
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
> Vous pouvez définir le bouton qui est ensuite à une autre clé pour l' **opérateur** à l’aide des **Options de Menu**. 
  
Vous pouvez définir l'opérateur comme suit :
  
- Un Skype pour Business Online utilisateur qui dispose d’un **Système téléphonique** de licence qui est activé pour Enterprise Voice ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé comme un opérateur. 
  
- Un autre standard automatique configuré dans votre organisation
    
- Une file d'attente existante configurée dans votre organisation. Pour plus d’informations sur les files d’attente des appels, consultez [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
### <a name="business-hours-and-call-handling"></a>Heures d'ouverture et traitement des appels

Les heures d'ouverture sont définies sur chaque standard automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures de bureau peut être définies avec sauts de temps au cours de la journée et toutes les heures qui ne sont pas définies comme heures ouvrées sont considérés comme étant en continu. Vous pouvez définir différentes options de gestion des appels entrantes et le message d’accueil différents (qui est facultatives) et à la fois peuvent être définies pour les heures de bureau et en continu.
  
Chaque standard automatique comprend des options de gestion des appels qui peuvent être définies :
  
- Vous pouvez définir la déconnexion de l'appel juste après le message d'accueil.
    
- Vous pouvez également :
    
  - Rediriger l’appel vers un Skype pour Business Online utilisateur qui dispose d’une licence de **Système téléphonique** est activé pour Enterprise Voice- ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge. 
  
  - Rediriger l’appel vers une file d’attente de l’appel. Pour plus d’informations sur les files d’attente des appels, consultez [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
  - Rediriger l’appel vers un autre standard automatique que vous avez configurées.
    
- Créer des options de menu et activer une invite de menu pour l'appelant. Par exemple : « Appuyez sur 1 pour contacter le département des ventes, appuyez sur 2 pour contacter le département des services. Pour contacter l'opérateur, appuyez sur 0 à tout moment. »
    
### <a name="menu-options"></a>Options de menu

Standards automatiques de système téléphonique permettent de créer des invites de menu (« appuyez sur 1 pour la vente, appuyez sur 2 pour les Services ») et définir les options de menu pour acheminer les appels en fonction de ce que l’utilisateur sélectionne. La configuration des options de menu d'un standard automatique permet à une organisation de fournir une assistance interactive pour orienter rapidement l'appelant vers sa destination, sans recourir à un opérateur humain pour la gestion des appels entrants. Invites peuvent être créés à l’aide de la synthèse vocale (invites généré par le système) ou en téléchargeant un fichier audio qui a été enregistré. La reconnaissance vocale utilise des commandes vocales pour naviguer en mode mains libres, mais les appelants peuvent également utiliser leur clavier téléphonique pour parcourir les menus.
  
Touches 0 à 9 peuvent être assignés aux **Options de Menu** dans un standard automatique à l’aide de la Skype entreprise centre d’administration. Plusieurs ensembles d'options de menu peuvent être créés pour les heures d'ouverture et de fermeture et vous pouvez activer ou désactiver la fonction Numérotation par nom dans les **Options de menus**. Les touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur, mappé vers la touche 0 par défaut. Toutefois, il peut être réaffecté à n’importe quelle autre touche ou supprimé du menu.
    
- Une file d’attente de l’appel.
    
- Un autre standard automatique. Menus à plusieurs niveaux peuvent être configurées en pointant une **Option de Menu** dans le standard automatique d’un à un autre standard automatique avec son propre ensemble d’Options de Menu, qui est appelée un standard automatique « imbriqués ».
    
- Un Skype pour Business Online utilisateur qui dispose d’un **Système téléphonique** de licence qui est activé pour Enterprise Voice ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé dans les **Options de Menu**. 
  
Le nom de chaque option de menu devient un mot clé de la reconnaissance vocale si la reconnaissance vocale a été activée. Par exemple, les appelants peuvent prononcer « One » pour sélectionner l’option de menu mappée à la clé 1, ou ils peuvent simplement dire « Sales » pour sélectionner l’option de menu même nommée « Sales ».
  
Pour configurer un standard automatique et les options de menu, consultez [configurer un standard automatique de système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Obtention de numéros de service pour un standard automatique

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Skype pour le centre d’administration Business** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - numéro gratuit **. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ou, si vous souhaitez transférer et le numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service. Accédez [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modifier l'ID de l’appelant de l’utilisateur pour le transformer en numéro de téléphone de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquez la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation, [l’ID d’appelant utilisation dans votre organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 