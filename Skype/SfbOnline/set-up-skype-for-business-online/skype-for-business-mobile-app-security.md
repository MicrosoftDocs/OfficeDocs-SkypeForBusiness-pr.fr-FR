---
title: Sécurité de l'application mobile Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Découvrez comment configurer la sécurité des applications mobiles pour vos utilisateurs. '
ms.openlocfilehash: f600230574b8d16a0f7907b4484da8ffcca6124e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239631"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="305b6-103">Sécurité de l'application mobile Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="305b6-103">Skype for Business mobile app security</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a><span data-ttu-id="305b6-104">Sécurité client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="305b6-104">Skype for Business Client Security</span></span>

<span data-ttu-id="305b6-105">Cet article contient des informations relatives au chiffrement des données dans les applications mobiles Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="305b6-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="305b6-106">**Nom d'utilisateur/Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="305b6-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="305b6-107">**Données d’application (conversations, <br/> liste de contacts, réunions)**</span><span class="sxs-lookup"><span data-stu-id="305b6-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="305b6-108">**Journaux de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="305b6-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="305b6-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="305b6-109">**Android**</span></span> <br/> |<span data-ttu-id="305b6-p101">Nous conservons des informations d'authentification dans Android Accounts. Ces données sont également chiffrées avant leur enregistrement. Le chiffrement s'effectue au moyen de l'algorithme « **AES/CBC/PKCS5Padding** ».</span><span class="sxs-lookup"><span data-stu-id="305b6-p101">We store credentials information in Android Accounts. We also encrypt credentials before saving them into Accounts. We use " **AES/CBC/PKCS5Padding** " algorithm for encryption. </span></span><br/> |<span data-ttu-id="305b6-p102">Elles sont conservées dans une base de données SQL à l'aide d'une bibliothèque nommée [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Nous utilisons leur algorithme par défaut, à savoir AES 256 bits, en mode CBC. Les données statiques sont toujours chiffrées dans le fichier de base de données et non chiffrées uniquement lors de leur transit dans la mémoire volatile et dans les piles d'appels de l'application. De plus, les fichiers de la messagerie vocale sont également chiffrés au moyen de la même méthode que le nom d'utilisateur et le mot de passe (ils ne sont pas stockés dans la base de données). Les messages vocaux sont déchiffrés sur le disque de façon temporaire pour permettre leur lecture.</span><span class="sxs-lookup"><span data-stu-id="305b6-p102">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/). We use their default algorithm of 256-bit AES in CBC mode. The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks. We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB). Voicemails are temporarily unencrypted on disk to allow playback.  </span></span><br/> |<span data-ttu-id="305b6-118">Cette information n'est pas chiffrée.</span><span class="sxs-lookup"><span data-stu-id="305b6-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="305b6-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="305b6-119">**iOS**</span></span> <br/> |<span data-ttu-id="305b6-p103">La combinaison nom d'utilisateur/mot de passe n'est PAS chiffrée dans le trousseau. Toutefois, le trousseau lui-même est chiffré.</span><span class="sxs-lookup"><span data-stu-id="305b6-p103">We DO NOT encrypt the username/password in the keychain. The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="305b6-p104">Nous utilisons déjà le système de protection des données [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) pour tous les fichiers stockés dans l'application. Cela signifie que les fichiers sont chiffrés jusqu'à ce que l'utilisateur déverrouille l'appareil pour la première fois après son redémarrage.</span><span class="sxs-lookup"><span data-stu-id="305b6-p104">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage. This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot. </span></span><br/> |<span data-ttu-id="305b6-124">Cette information n'est pas chiffrée.</span><span class="sxs-lookup"><span data-stu-id="305b6-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="305b6-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="305b6-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="305b6-p105">Windows Phone utilise DPAPI (API de protection des données) pour sécuriser les mots de passe dans Windows. Il me semble que la méthode de chiffrement utilisée est AES. Windows n'offre pas la possibilité de configurer la taille de la clé (ou la méthode). Il faut s'en remettre à ce que DPAPI propose. Cette méthode utilise le TPM de l'appareil pour sécuriser les clés propres à l'utilisateur et à l'appareil. Notez que les clés DPAPI ne sont pas propres à l'application.</span><span class="sxs-lookup"><span data-stu-id="305b6-p105">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords. I believe the encryption scheme used is AES. Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives. It will use the device TPM to secure keys which are specific to the user and device. Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="305b6-p106">Les données d'application Windows Phone sont protégées par [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, à l'instar des informations d'authentification. Selon le niveau de détail souhaité, puisque certaines informations de l'index pour les données d'application sont protégées par un chiffrement AES (pas DPAPI) pour éviter le salting, nous pouvons donc les consulter sans procéder au déchiffrement et la clé est à son tour protégée par DPAPI. Les données mises en cache peuvent être lues par n'importe quelle méthode par le même téléphone, si celui-ci est en mesure d'accéder à notre dossier de données. Le chiffrement Windows ne protège pas des tentatives d'accès via le bac à sable, uniquement des tentatives d'accès externes.</span><span class="sxs-lookup"><span data-stu-id="305b6-p106">WP App Data is protected with [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, like the creds. Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI. Cached data can be read by any process from the same phone, assuming it can reach our data folder. Windows encryption does not protect from sandbox breach, only external access attempts.  </span></span><br/> |<span data-ttu-id="305b6-135">Cette information n'est pas chiffrée.</span><span class="sxs-lookup"><span data-stu-id="305b6-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="305b6-136">**Remarque :** Reportez-vous [à cette documentation publique pour la](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) mise en œuvre de l’épingle de périphérique disponible sur chacune des plateformes mobiles ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="305b6-136">**Note:** Please refer to [this public documentation](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="305b6-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="305b6-137">Related topics</span></span>
[<span data-ttu-id="305b6-138">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="305b6-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="305b6-139">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="305b6-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
