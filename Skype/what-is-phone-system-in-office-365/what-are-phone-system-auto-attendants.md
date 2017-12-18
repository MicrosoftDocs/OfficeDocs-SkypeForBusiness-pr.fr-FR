---
title: "Quelles sont les standards automatiques système téléphonique ?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# Quelles sont les standards automatiques système téléphonique ?

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Système téléphonique dans Office 365 standards automatiques pouvant être utilisées pour créer un système de menus pour votre organisation qui permet aux appelants internes et externes se déplacer parmi un système de menus localiser et placer ou transférer des appels aux utilisateurs de la société ou départements de votre organisation.
  
Lorsque vous appellent de personnes, elles sont présentées avec une série d'invites vocales qui leur permettent de passer un appel à un utilisateur ou recherchez une personne de votre organisation, puis placez un appel à cet utilisateur. Un standard automatique est une série d'invites vocales ou un fichier audio que les appelants entendront au lieu d'un opérateur humain lorsqu'ils participer à une organisation. Un standard automatique permet aux appelants parcourir le système de menus, passer des appels, ou recherchez des utilisateurs à l'aide d'un clavier de téléphone (DTMF) ou entrées à l'aide de la reconnaissance vocale de la voix.
  
Pour configurer un standard automatique pour le système téléphonique dans Office 365, accédez [Configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
  
Un standard automatique de système téléphonique comporte les fonctionnalités suivantes :
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
    
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
    
- Il propose recherche dans l'annuaire qui permet aux personnes qui rejoignent pour effectuer une recherche dans l'annuaire l'organisation un nom.
    
- Il permet à une personne qui dans les appels à atteindre ou laisser un message d'une personne de votre organisation.
    
## Mise en route

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum) une licence entreprise E3 plus **Système téléphonique** ou une licence entreprise E5. Le nombre de licences utilisateur **Système téléphonique** affectés impacts le nombre de service aux nombres qui est disponible à utiliser pour les standards automatiques. Le nombre de standards automatiques que vous pouvez avoir dépend du nombre **Système téléphonique** et **Audioconférence** des licences qui sont affectées dans votre organisation. Pour en savoir plus sur les licences, accédez[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu est un utilisateur en ligne avec une licence **Système téléphonique**, vous devez les activer pour Enterprise Voice ou leur affecter des Plans de l'appel. Voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez également utiliser Windows PowerShell. Par exemple exécuter :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros de service gratuit pour vos standards automatiques, vous devez configurer les Communications crédits. Pour ce faire, voir [Que sont les Communications crédits ?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) et[Configurer les Communications crédits pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
## Présentation de la fonctionnalité

### Numérotation par nom

Numérotation par nom est une fonctionnalité d'un standard automatique qui est appelé recherche dans l'annuaire. Il active les personnes qui appellent votre standard automatique à permet d'entrer un nom complet ou partiel permet de rechercher répertoire de société, localisez la personne qui et avez puis transférer l'appel vers ces signets à voix (reconnaissance vocale) ou leur pavé numérique du téléphone (DTMF). Si vous disposez Skype entreprise Online utilisateurs, **ils ne sont pas obligatoires pour qu'un numéro de téléphone ou ont l'appel d'offre affectés, mais ils doivent avoir une licence **Système téléphonique**** pour les rendre accessibles lorsqu'ils effectuent une recherche à l'aide de numérotation par son nom. Numérotation par nom pourront même rechercher et transférer des appels vers Skype pour les utilisateurs d'entreprise Online qui sont hébergés dans différents pays ou régions pour les organisations multinationales.
  
> [!CAUTION]
> Déploiements sur site d'utilisateurs de Lync Server 2010 ne sont pas répertoriés dans l'annuaire lorsqu'une personne recherche pour eux. 
  
### Taille de l'annuaire maximale

Il n'existe aucune limite sur la taille d'Active Directory pour lesquels Dial par nom est pris en charge lors de l'utilisation du pavé numérique du téléphone pour rechercher pour entrer des noms partielles ou complètes (prénom nom et également nom + prénom). Toutefois, la taille maximale pour le nom qu'un standard automatique unique peut prendre en charge à l'aide de la reconnaissance nom avec la voix est 80 000 utilisateurs.
  
||||
|:-----|:-----|:-----|
|**Type d'entrée** <br/> |**Format de recherche** <br/> |**Nombre maximal d'utilisateurs dans une organisation** <br/> |
|DTMF (entrée de clavier de téléphone)  <br/> |Partiel  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |Aucune limite stricte  <br/> |
|Voix (entrée vocale)  <br/> |Prénom  <br/> Nom  <br/> Prénom + nom  <br/> Nom + prénom  <br/> |80 000 utilisateurs  <br/> |
   
> [!NOTE]
> Si vous utilisez numérotation par nom avec la voix de reconnaissance, mais Active Directory de votre organisation est supérieure à 80 000 utilisateurs et vous n'avez pas limité la portée de numérotation par un nom à l'aide de la fonctionnalité de numérotation étendue, numérotation par nom fonctionnera toujours pour vos interlocuteurs à l'aide d'un clavier de téléphone , et entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité étendue de numérotation pour affiner les noms sont accessibles en modifiant l'étendue de numérotation par un nom pour un standard automatique particulier. 
  
### Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Personnes se connectant permet de communiquer aux utilisateurs en spécifiant soit le nom complet ou partiel de la personne qu'il tente d'atteindre numérotation par son nom. La bonne chose est qu'il existe différents formats qui peuvent être utilisés lorsque le nom est entré.
  
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
   
Il existe plusieurs caractères spéciaux qui sont utilisés lorsque vous recherchez des personnes à l'aide d'un clavier téléphonique. Par exemple, l'utilisateur est invité à utiliser dièse (#), tandis que la touche zéro (0) est utilisé pour un espace entre les noms. En appuyant sur la touche étoile (*) répète la liste des noms à la personne correspondants.
  
|||
|:-----|:-----|
|**Caractère spécial du clavier téléphonique** <br/> |**Signification** <br/> |
|# (touche dièse)  <br/> |Caractère de fin de saisie d'un nom  <br/> |
|0 (zéro)  <br/> |Espace entre les noms  <br/> |
|* (touche étoile)  <br/> |Répétition de la liste de correspondances de noms  <br/> |
   
### Numérotation par nom - Reconnaissance vocale de nom

Personnes rechercher d'autres personnes dans leur organisation à l'aide de la voix (reconnaissance vocale). Ils également communiquer avec tout le monde dans Active Directory de la société en indiquant le nom de la personne qu'ils vous recherchez. À l'aide d'entrées vocales peut reconnaître les noms dans différents formats, y compris le prénom, nom, prénom nom, ou nom + prénom.
  
Lorsque vous activez la reconnaissance vocale pour un standard automatique, entrée pavé numérique du téléphone (DTMF) ne sont pas désactivée, les deux types d'entrée peuvent être utilisée. Entrée du clavier téléphonique ne peut pas être désactivée et peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
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
> Il peut prendre jusqu'à 36 heures pour un utilisateur pour que leur nom apparaît dans le répertoire pour les appels par nom avec la reconnaissance vocale. 
  
### Prise en charge des langues

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
   
Les commandes vocales suivantes sont disponibles dans les quatorze (14﻿) langues prises en charge par la reconnaissance vocale :
  
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
   
### Utilisation de l'option opérateur

L'utilisation de l'opérateur d'un standard automatique est un paramètre facultatif qui permet à l'appelant de contacter une personne.
  
La touche 0 et la commande vocale « Opérateur » (dans toutes les langues prises en charge par la reconnaissance vocale) sont affectées à l'opérateur par défaut.
  
> [!NOTE]
> Vous pouvez définir le bouton qui a été basculé pour l' **opérateur** à une autre clé à l'aide des **Options du Menu**. 
  
Vous pouvez définir l'opérateur comme suit :
  
- Un Skype pour entreprise Online utilisateur disposant d'un **Système téléphonique** licence qui est activé pour voix entreprise ou leur a l'appel d'offre affecté. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez les appels soient automatiquement transférés directement vers la messagerie vocale de cette personne.
    
    > [!NOTE]
    > Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne peut pas être utilisé comme un opérateur. 
  
- Un autre standard automatique configuré dans votre organisation
    
- N'importe quel appel file d'attente existante qui a été configurée dans votre organisation. Pour en savoir plus sur les files d'appel, voir [Créer une file d'attente des appels système téléphonique](create-a-phone-system-call-queue.md).
    
### Heures d'ouverture et traitement des appels

Les heures de bureau sont définies sur chaque standard automatique. Si les heures de bureau ne sont pas définies, tous les jours et toutes les heures dans la journée sont considérés comme les heures de bureau, car un calendrier 24/7 est défini par défaut. Heures de travail peut être définies avec des sauts de dans le temps pendant la journée et toutes les heures qui ne sont pas définies comme les heures de bureau sont considérés comme en continu. Vous pouvez définir différentes options de gestion d'appel entrantes et le message d'accueil différents (qui est facultatif), puis deux peuvent être définies pour les heures de bureau et en continu.
  
Chaque standard automatique comporte les options de gestion des appels pouvant être définies :
  
- Vous pouvez définir la déconnexion de l'appel juste après le message d'accueil.
    
- Vous pouvez également :
    
  - Rediriger l'appel vers un Skype pour entreprise Online utilisateur possédant une licence de **Système téléphonique** est activé voix entreprise ou a l'appel d'offre attribuée. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez les appels soient automatiquement transférés directement vers la messagerie vocale de cette personne.
    
    > [!NOTE]
    > Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne sont pas pris en charge. 
  
  - Rediriger l'appel vers une file d'attente d'appel. Pour en savoir plus sur les files d'appel, voir [Créer une file d'attente des appels système téléphonique](create-a-phone-system-call-queue.md).
    
  - Rediriger l'appel vers un autre standard automatique que vous avez configuré
    
- Créer des options de menu et activer une invite de menu pour l'appelant. Par exemple : « Appuyez sur 1 pour contacter le département des ventes, appuyez sur 2 pour contacter le département des services. Pour contacter l'opérateur, appuyez sur 0 à tout moment. »
    
### Options de menu

Standards automatiques de système téléphonique permettent de créer des invites de menu (« appuyez sur 1 pour les ventes, appuyez sur 2 pour les Services ») et définir les options de menu à acheminer les appels en fonction de ce que l'utilisateur sélectionne. Configuration des options de menu pour un standard automatique permet à une organisation de fournir un guide interactif pour obtenir la personne à leur destination plus rapidement, sans avoir recours à un opérateur humain pour traiter les appels entrants. Menu invites peuvent être créés à l'aide de synthèse vocale (invites générées par le système) ou en téléchargeant un fichier audio qui a été enregistré. La reconnaissance vocale utilise les commandes vocales pour naviguer mains libres, mais les personnes se connectant pouvez également utiliser le pavé numérique du téléphone pour naviguer dans les menus.
  
Touches 0 à 9 peuvent être affectées aux **Options de Menu** dans un standard automatique à l'aide de la Skype centre d'administration entreprise. Différents jeux d'options de menu peuvent être créés pour les heures de bureau et après les heures, et vous pouvez activer ou désactiver la numérotation par nom dans les **Options du Menu**. Touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur qui est mappé principales 0 par défaut. Toutefois, il peut être réaffecter à une autre touche ou supprimé du menu.
    
- Une file d'attente de l'appel.
    
- Un autre standard automatique. Menus à plusieurs niveaux peuvent être configurés en pointant une **Option de Menu** de standard un automatique sur un autre standard automatique avec son propre jeu d'Options de Menu qui s'appelle un standard automatique « imbriquée ».
    
- Un Skype pour entreprise Online utilisateur disposant d'un **Système téléphonique** licence qui est activé pour voix entreprise ou leur a l'appel d'offre affecté. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez les appels soient automatiquement transférés directement vers la messagerie vocale de cette personne.
    
    > [!NOTE]
    > Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne peuvent pas être utilisé dans les **Options de Menu**. 
  
Le nom de chaque option de menu devient un mot clé reconnaissance vocale si la reconnaissance vocale a été activée. Par exemple, appelants pouvant dites « Un » pour sélectionner l'option de menu mappée à clé 1, ou qu'ils peuvent simplement dites « Ventes » pour sélectionner l'option de menu même nommée « Ventes ».
  
Pour configurer un standard automatique et des options de menu, cliquez [Configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
  
### Obtention de numéros de service pour un standard automatique

Avant de pouvoir créer et configurer vos standards automatiques, vous devrez obtenir ou transférer votre numéro payant existant ou un service gratuit nombres. Une fois que vous obtenez le numéro payant ou gratuit service des numéros de téléphone, ils seront affichent dans la **Skype centre d'administration entreprise** > **vocale** > **numéros de téléphone** et l'est de **type numérique** répertorié être répertoriée en tant que **Service - gratuit**. Pour obtenir vos numéros de service, voir les [Obtention des numéros de téléphone des services Skype Entreprise](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ou, si vous souhaitez transférer et numéro de service existant, voir[Transférer des numéros de téléphone vers Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype centre d'administration entreprise pour obtenir des numéros de service. Accédez [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour apprendre à le faire.
  
## Modification des ID de l'appelant de l'utilisateur pour être numéro de téléphone d'un appel la file d'attente

Vous pouvez protéger identité d'un utilisateur en modifiant leur ID d'appelant pour les appels sortants à appel en attente à la place en créant une stratégie à l'aide de l'applet de commande **New-CallingLineIdentity**.
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l'utilisateur à l'aide de l'applet de commande **Grant-CallingLineIdentity**. Pour ce faire, exécutez :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d'informations sur la façon de modifier les paramètres d'ID de l'appelant dans votre organisation [Comment utiliser un ID d'appelant dans votre organisation](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Rubriques connexes

[Voici ce que vous obtenez avec système téléphonique dans Office 365](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[Configurer l'appel d'offre](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

