---
title: Expanseur des paramètres généraux du serveur de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN. Les paramètres suivants se trouvent dans chaque section :'
ms.openlocfilehash: 43fb20304a078c7d51024153e7a725992fb95280
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612423"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010

Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN. Les paramètres suivants se trouvent dans chaque section :

 **Général**:

- **Nom de domaine complet :** vous modifiez le nom de domaine complet du serveur de médiation

- **Associations**: cochez la case Associer un pool de serveurs Edge (pour les **composants multimédias)** et sélectionnez un serveur Edge ou un pool de serveurs Edge pour le serveur de médiation à utiliser comme chemin d’accès multimédia pour l’accès externe.

  **Tronçon suivant** :

- **Sélection du saut** suivant : sélectionnez dans une liste le serveur frontal ou le pool frontal à utiliser comme chemin d’accès pour le serveur de médiation à utiliser pour communiquer avec votre déploiement.

  **Passerelle PSTN** :

  **Passerelle PSTN du serveur de médiation** :

- **Ports d’écoute**: définissez les ports que le serveur de médiation écoutera. Vous pouvez définir un port pour le protocole **TLS** (Transport Layer Security) ou **TCP** (Transport Control Protocol). Pour que l’entrée du port TCP soit disponible, vous devez activer la case à cocher **Activer le port TCP**.

    > [!IMPORTANT]
    > Consultez la documentation et les paramètres de configuration de votre passerelle de réseau téléphonique commuté (PSTN) pour déterminer si vous devez activer et définir les valeurs du port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Certaines passerelles PSTN ne prennent pas en charge TLS.

- Il existe une liste de jonctions SIP et de passerelles qui sont définies et configurées pour votre déploiement. Si aucune entrée n’est présente, aucune jonction SIP ou passerelles PSTN n’est configurée pour votre déploiement. Vous définissez et configurez les passerelles et les trunks sous **Composants partagés** dans le Générateur de topologie.

## <a name="see-also"></a>Voir aussi

[Vue d’ensemble d’une jonction SIP](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[Options de déploiement d’une passerelle PSTN](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)