---
title: Configurer le serveur de médiation
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurer le serveur de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Cette procédure décrit la procédure de configuration du pool Lync Server 2013 de manière à utiliser le serveur de médiation Lync Server 2013 au lieu du serveur de médiation traditionnel d’Office Communications Server 2007 R2.

Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les droits d’administrateur et les autorisations nécessaires pour ajouter des rôles de serveur. Pour plus d’informations, voir autorisations de configuration de délégué dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server. Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

<div>


> [!NOTE]  
> Pour obtenir les dernières informations sur la recherche de passerelles RTC, de PBX IP et de services d’agrégation de messages SIP qualifiés compatibles avec Lync Server 2013, voir « Microsoft Unified Communications Open <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Interoperability » à l’adresse.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Pour configurer la médiation serveur à l’aide du générateur de topologie

1.  Ouvrez une topologie existante à partir du générateur de topologie.

2.  Dans le volet gauche, sélectionnez **passerelles RTC**.

3.  Cliquez avec le bouton droit sur **passerelles RTC**, puis cliquez sur **nouvelle passerelle IP/PSTN**.

4.  Complétez la page **définir une nouvelle passerelle IP/RTC** en utilisant les informations suivantes :
    
      - Entrez le nom de domaine complet ou l’adresse IP de la passerelle. Le FQDN de la passerelle est requis si la passerelle utilise le protocole TLS.
    
      - Acceptez la valeur par défaut du **port d’écoute pour la passerelle IP/PSTN** ou entrez le nouveau port d’écoute s’il a été modifié.
    
      - Définissez le **protocole de transport SIP**.

5.  Dans le volet gauche, accédez au **pool frontal d’Enterprise Edition** ou au **serveur Standard Edition Server**.

6.  Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

7.  Sous **serveur de médiation**, définissez les **ports Listening**.

8.  Ensuite, associez la passerelle RTC nouvellement créée en la sélectionnant et en cliquant sur **Ajouter**.

9.  Dans **Générateur de topologie**, sélectionnez le **serveur Lync**le plus en tête de nœud.

10. Dans le menu **action** , sélectionnez la **topologie de publication** , puis cliquez sur **suivant**.

11. Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.

<div>


> [!NOTE]  
> Il est important que vous complétiez le sujet suivant, que vous <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Modifiez les itinéraires vocaux pour utiliser le nouveau serveur de médiation Lync Server 2013</A> pour vous assurer que les itinéraires vocaux pointent vers le serveur de médiation approprié.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

