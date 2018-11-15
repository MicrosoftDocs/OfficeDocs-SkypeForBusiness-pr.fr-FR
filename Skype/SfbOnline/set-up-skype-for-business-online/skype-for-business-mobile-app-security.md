---
title: Sécurité de l'application mobile Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Apprenez à configurer la sécurité des applications mobiles pour vos utilisateurs. '
ms.openlocfilehash: 03b6575826defd5bd4c8c7739a1975edaabe0752
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530614"
---
# <a name="skype-for-business-mobile-app-security"></a>Sécurité de l'application mobile Skype Entreprise

## <a name="skype-for-business-client-security"></a>Sécurité client Skype Entreprise

Cet article contient des informations relatives au chiffrement des données dans les applications mobiles Skype Entreprise.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nom d'utilisateur/Mot de passe** <br/> |**Données d’application (Conversations,<br/> liste, les réunions des contacts)** <br/> |**Journaux de diagnostic** <br/> |
|**Android** <br/> |Nous conservons des informations d'authentification dans Android Accounts. Ces données sont également chiffrées avant leur enregistrement. Le chiffrement s'effectue au moyen de l'algorithme « **AES/CBC/PKCS5Padding** ».<br/> |Elles sont conservées dans une base de données SQL à l'aide d'une bibliothèque nommée [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Nous utilisons leur algorithme par défaut, à savoir AES 256 bits, en mode CBC. Les données statiques sont toujours chiffrées dans le fichier de base de données et non chiffrées uniquement lors de leur transit dans la mémoire volatile et dans les piles d'appels de l'application. De plus, les fichiers de la messagerie vocale sont également chiffrés au moyen de la même méthode que le nom d'utilisateur et le mot de passe (ils ne sont pas stockés dans la base de données). Les messages vocaux sont déchiffrés sur le disque de façon temporaire pour permettre leur lecture.<br/> |Cette information n'est pas chiffrée.  <br/> |
|**iOS** <br/> |La combinaison nom d'utilisateur/mot de passe n'est PAS chiffrée dans le trousseau. Toutefois, le trousseau lui-même est chiffré.  <br/> |Nous utilisons déjà le système de protection des données [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) pour tous les fichiers stockés dans l'application. Cela signifie que les fichiers sont chiffrés jusqu'à ce que l'utilisateur déverrouille l'appareil pour la première fois après son redémarrage.<br/> |Cette information n'est pas chiffrée.  <br/> |
|**Windows Phone** <br/> |Windows Phone utilise DPAPI (API de protection des données) pour sécuriser les mots de passe dans Windows. Il me semble que la méthode de chiffrement utilisée est AES. Windows n'offre pas la possibilité de configurer la taille de la clé (ou la méthode). Il faut s'en remettre à ce que DPAPI propose. Cette méthode utilise le TPM de l'appareil pour sécuriser les clés propres à l'utilisateur et à l'appareil. Notez que les clés DPAPI ne sont pas propres à l'application.  <br/> |Les données d'application Windows Phone sont protégées par [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, à l'instar des informations d'authentification. Selon le niveau de détail souhaité, puisque certaines informations de l'index pour les données d'application sont protégées par un chiffrement AES (pas DPAPI) pour éviter le salting, nous pouvons donc les consulter sans procéder au déchiffrement et la clé est à son tour protégée par DPAPI. Les données mises en cache peuvent être lues par n'importe quelle méthode par le même téléphone, si celui-ci est en mesure d'accéder à notre dossier de données. Le chiffrement Windows ne protège pas des tentatives d'accès via le bac à sable, uniquement des tentatives d'accès externes.<br/> |Cette information n'est pas chiffrée.  <br/> |
   
**Remarque :** Reportez-vous à [cette documentation publique](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) pour l’application de code confidentiel périphérique disponible sur chacun des plateformes mobiles ci-dessus
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 