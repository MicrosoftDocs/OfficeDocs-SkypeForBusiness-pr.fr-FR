---
title: "Skype pour la sécurité de mobile application métier"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Apprenez à configurer la sécurité d’une application mobile pour vos utilisateurs. "
ms.openlocfilehash: bc80434cb29f6d2133ce99e9a583cb388fc7b1b3
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-mobile-app-security"></a>Skype pour la sécurité de mobile application métier

## <a name="skype-for-business-client-security"></a>Skype pour la sécurité du Client entreprise

Cet article décrit les informations de chiffrement de données sur Skype pour les applications métier mobiles.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nom d’utilisateur/mot de passe** <br/> |**Données de l’application (Conversations,<br/> liste, réunions de contacts)** <br/> |**Journaux de diagnostic** <br/> |
|**Android** <br/> |Nous stockons les informations d’identification de comptes Android. Nous avons également crypter des informations d’identification avant de les enregistrer dans les comptes. Nous utilisons des « **AES/CBC/PKCS5Padding** » algorithme pour le chiffrement. <br/> |Nous stocker dans une base de données SQL cryptée à l’aide d’une bibliothèque appelée [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Nous utilisons leur algorithme par défaut de 256 bits AES en mode CBC. Les données au repos sont toujours chiffrées dans le fichier de base de données et sont uniquement non chiffrées en transit à l’intérieur de piles de mémoire et appelez volatiles de l’application. Nous avons également chiffrer les fichiers de messagerie vocale à l’aide de la même méthode en tant que nom d’utilisateur et mot de passe cryptage (ils ne sont pas stockés dans la base de données). Messages vocaux est temporairement non cryptées sur le disque pour autoriser la lecture.  <br/> |Ces informations ne sont pas cryptées.  <br/> |
|**e/s** <br/> |Nous ne pas crypter le nom d’utilisateur/mot de passe dans le trousseau. La chaîne de clé est cryptée, toutefois, sur son propre.  <br/> |Nous utilisons déjà indicateur de protection de données [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) sur tous les fichiers dans le stockage de l’application. Cela signifie que les fichiers dans le stockage d’application seraient être cryptés jusqu'à ce que l’utilisateur déverrouille le périphérique pour la première fois après le redémarrage du périphérique. <br/> |Ces informations ne sont pas cryptées.  <br/> |
|**Windows Phone** <br/> |Windows Phone utilise DPAPI (API de Protection des données) dans Windows pour sécuriser les mots de passe. Je pense que le schéma de cryptage utilisé est AES. Windows ne nous donne pas une option pour configurer le taille de clé (ou le schéma), il est tout ce que donne la DPAPI. Il utilise le périphérique module de plateforme sécurisée pour sécuriser des clés qui sont spécifiques à l’utilisateur et d’un périphérique. Notez que les clés DPAPI ne sont pas spécifiques à l’application.  <br/> |WP App Data protégées avec [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx), vous plaisent la Réf.. En fonction de la quantité de détails que nous, les informations d’index pour les données de l’application est protégé par le cryptage AES (non DPAPI) afin d’éviter le salage, donc nous pouvons rechercher sans décryptage, et cette clé est ensuite protégée par DPAPI. Données mises en cache peuvent être lus par n’importe quel processus à partir du téléphone même, en supposant qu’il peut atteindre notre dossier de données. Chiffrement Windows ne protège pas contre la violation de sandbox, tente d’accès externe uniquement.  <br/> |Ces informations ne sont pas cryptées.  <br/> |
   
**Remarque :** Veuillez consulter [cette documentation publique](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) pour application de broche de périphérique disponible sur chacune des plates-formes mobiles ci-dessus
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels](let-skype-for-business-users-add-skype-contacts.md)
