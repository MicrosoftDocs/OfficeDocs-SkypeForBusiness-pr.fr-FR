---
title: Expanseur des paramètres généraux du serveur de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN. Les paramètres suivants se trouvent dans chaque section :'
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215155"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres généraux du serveur de médiation pour Lync Server 2010

Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN. Les paramètres suivants se trouvent dans chaque section :

 **Général**:

- Nom de domaine **complet**: modifiez le nom de domaine complet du serveur de médiation.

- **Associations**: activez la case à cocher **associer un pool Edge (pour les composants multimédias)** et sélectionnez un serveur Edge ou un pool de serveurs Edge pour le serveur de médiation à utiliser comme chemin de média pour l’accès externe.

  **Tronçon suivant** :

- **Sélection du tronçon suivant**: sélectionnez dans une liste le serveur frontal ou le pool frontal à utiliser comme chemin d’accès pour le serveur de médiation à utiliser pour communiquer avec votre déploiement.

  **Passerelle PSTN** :

  **Passerelle PSTN du serveur de médiation** :

- **Ports d’écoute**: définissez les ports que le serveur de médiation doit écouter. Vous pouvez définir un port pour le protocole **TLS** (Transport Layer Security) ou **TCP** (Transport Control Protocol). Pour que l’entrée du port TCP soit disponible, vous devez activer la case à cocher **Activer le port TCP**.

    > [!IMPORTANT]
    > Consultez la documentation et les paramètres de configuration de votre passerelle de réseau téléphonique commuté (PSTN) pour déterminer si vous devez activer et définir les valeurs du port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Certaines passerelles PSTN ne prennent pas en charge TLS.

- Il existe une liste de jonctions SIP et de passerelles qui sont définies et configurées pour votre déploiement. Si aucune entrée n’est présente, aucune jonction SIP ou passerelles PSTN n’est configurée pour votre déploiement. Vous définissez et configurez des jonctions et des passerelles sous **composants partagés** dans le générateur de topologie.

## <a name="see-also"></a>Voir aussi

[Vue d’ensemble d’une jonction SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Options de déploiement d’une passerelle PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
