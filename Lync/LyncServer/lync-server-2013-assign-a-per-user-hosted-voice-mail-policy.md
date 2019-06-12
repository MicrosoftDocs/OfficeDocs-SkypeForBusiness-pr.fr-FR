---
title: 'Lync Server 2013: affectation d’une stratégie de messagerie vocale hébergée par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846940"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Affecter une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013

 


Le déploiement d’une ou plusieurs stratégies de messagerie vocale hébergées par utilisateur est facultatif. Si vous déployez des stratégies par utilisateur, vous devez les affecter explicitement aux utilisateurs, groupes ou objets de contact.

Pour plus d’informations sur l’attribution ou la suppression de l’attribution de stratégies de messagerie vocale hébergées par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Pour attribuer une stratégie de messagerie vocale hébergée par utilisateur

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de passe Grant-CsHostedVoicemailPolicy pour affecter la stratégie de messagerie vocale hébergée par utilisateur à des utilisateurs, des groupes et des objets de contact individuels. Par exemple, exécutez :
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    Dans cet exemple, la stratégie de messagerie vocale hébergée exredmond est affectée à l’utilisateur Ken Myer.
    
    **Identité** indique le compte d’utilisateur à modifier. La valeur IDENTITY peut être spécifiée en utilisant l’un des formats suivants:
    
      - Adresse SIP de l’utilisateur
    
      - Nom d’utilisateur principal d’Active Directory de l’utilisateur
    
      - Le nom de connexion\\au domaine de l’utilisateur (par\\exemple, contoso kenmyer);
    
      - Nom d’affichage des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer). Si vous utilisez le nom d’affichage comme valeur d’identité, vous pouvez utiliser le caractère\*générique astérisque (). Par exemple, l’identité «\* Smith» renvoie tous les utilisateurs qui ont un nom d’affichage qui se termine par la valeur de chaîne «Smith».
    

    > [!NOTE]  
    > Le nom de compte SAM-nom Active Directory de l’utilisateur ne peut pas être utilisé en tant que valeur d’identité, car le nom de compte SAM n’est pas nécessairement unique dans la forêt.


