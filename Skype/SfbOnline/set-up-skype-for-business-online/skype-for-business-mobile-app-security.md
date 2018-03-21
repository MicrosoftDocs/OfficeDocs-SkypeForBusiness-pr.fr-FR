---
title: "Skype pour la sécurité de mobile application métier"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Apprenez à configurer la sécurité d’une application mobile pour vos utilisateurs. "
ms.openlocfilehash: 150eb50c4e2c57b3e51b9400d9fdb79d49990174
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-mobile-app-security"></a>Skype pour la sécurité de mobile application métier

## <a name="skype-for-business-client-security"></a>Sécurité client Skype Entreprise

Cet article contient des informations relatives au chiffrement des données dans les applications mobiles Skype Entreprise.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nom d'utilisateur/Mot de passe** <br/> |**Données de l’application (Conversations,<br/> liste, réunions de contacts)** <br/> |**Journaux de diagnostic** <br/> |
|**Android** <br/> |Nous conservons des informations d'authentification dans Android Accounts. Ces données sont également chiffrées avant leur enregistrement. Le chiffrement s'effectue au moyen de l'algorithme « **AES/CBC/PKCS5Padding** ».<br/> |Elles sont conservées dans une base de données SQL à l'aide d'une bibliothèque nommée [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Nous utilisons leur algorithme par défaut, à savoir AES 256 bits, en mode CBC. Les données statiques sont toujours chiffrées dans le fichier de base de données et non chiffrées uniquement lors de leur transit dans la mémoire volatile et dans les piles d'appels de l'application. De plus, les fichiers de la messagerie vocale sont également chiffrés au moyen de la même méthode que le nom d'utilisateur et le mot de passe (ils ne sont pas stockés dans la base de données). Les messages vocaux sont déchiffrés sur le disque de façon temporaire pour permettre leur lecture.<br/> |Cette information n'est pas chiffrée.  <br/> |
|**e/s** <br/> |La combinaison nom d'utilisateur/mot de passe n'est PAS chiffrée dans le trousseau. Toutefois, le trousseau lui-même est chiffré.  <br/> |Nous utilisons déjà le système de protection des données [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) pour tous les fichiers stockés dans l'application. Cela signifie que les fichiers sont chiffrés jusqu'à ce que l'utilisateur déverrouille l'appareil pour la première fois après son redémarrage.<br/> |Cette information n'est pas chiffrée.  <br/> |
|**Windows Phone** <br/> |Windows Phone utilise DPAPI (API de protection des données) pour sécuriser les mots de passe dans Windows. Il me semble que la méthode de chiffrement utilisée est AES. Windows n'offre pas la possibilité de configurer la taille de la clé (ou la méthode). Il faut s'en remettre à ce que DPAPI propose. Cette méthode utilise le TPM de l'appareil pour sécuriser les clés propres à l'utilisateur et à l'appareil. Notez que les clés DPAPI ne sont pas propres à l'application.  <br/> |Les données d'application Windows Phone sont protégées par [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, à l'instar des informations d'authentification. Selon le niveau de détail souhaité, puisque certaines informations de l'index pour les données d'application sont protégées par un chiffrement AES (pas DPAPI) pour éviter le salting, nous pouvons donc les consulter sans procéder au déchiffrement et la clé est à son tour protégée par DPAPI. Les données mises en cache peuvent être lues par n'importe quelle méthode par le même téléphone, si celui-ci est en mesure d'accéder à notre dossier de données. Le chiffrement Windows ne protège pas des tentatives d'accès via le bac à sable, uniquement des tentatives d'accès externes.<br/> |Cette information n'est pas chiffrée.  <br/> |
   
**Remarque :** Veuillez consulter [cette documentation publique](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) pour application de broche de périphérique disponible sur chacune des plates-formes mobiles ci-dessus
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
