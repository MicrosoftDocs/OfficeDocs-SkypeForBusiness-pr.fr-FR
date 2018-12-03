---
title: Configurer le serveur de médiation
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurer le serveur de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification :** 09-2012-28_

Cette procédure détaille les étapes pour configurer le pool Lync Server 2013 pour utiliser le serveur de médiation Lync Server 2013, au lieu du hérité Office Communications Server 2007 R2 Mediation Server.

Pour publier avec succès, activer ou désactiver une topologie lors de l’ajout ou suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et administrateurs du domaine. Il est également possible de déléguer les droits d’administrateur approprié et les autorisations permettant d’ajouter des rôles de serveur. Pour plus d’informations, voir Delegate Setup Permissions dans le serveur Standard Edition server ou Enterprise Edition server documentation de déploiement. Autres modifications de configuration, pour seulement l’appartenance au groupe RTCUniversalServerAdmins est requis.

<div>


> [!NOTE]  
> Pour obtenir les dernières informations sur la recherche de passerelles PSTN qualifiées, IP-PBX et services d’acheminement SIP qui fonctionnent avec Lync Server 2013, voir « Microsoft Unified Communications programme Open Interoperability » à <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Pour configurer Mediation Server à l’aide de générateur de topologies

1.  Ouvrez une topologie existante du Générateur de topologie.

2.  Dans le volet gauche, accédez à **passerelles PSTN**.

3.  Avec le bouton droit de **passerelles PSTN**, puis cliquez sur **Nouvelle passerelle IP/RTC**.

4.  Configurez la page **Définir une nouvelle passerelle IP/RTC** avec les informations suivantes :
    
      - Entrez la nom de domaine complet ou l’adresse IP de passerelle. Le nom de domaine complet de la passerelle est requis si la passerelle utilise le protocole TLS.
    
      - Acceptez la valeur par défaut du **port d’écoute pour la passerelle IP/PSTN** ou entrez le nouveau port d’écoute s’il a été modifié.
    
      - Définir le **protocole de Transport de Sip**.

5.  Dans le volet de gauche, naviguez vers le **pool frontal Enterprise Edition** ou le **Serveur Standard Edition Server**.

6.  Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.

7.  Sous **Serveur de médiation**, de configurer les **ports d’écoute**.

8.  Ensuite, associez la passerelle PSTN nouvellement créée en la sélectionnant et en cliquant sur **Ajouter**.

9.  Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

10. Dans le menu **Action** , sélectionnez **Publier la topologie** , puis cliquez sur **suivant**.

11. Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant.

<div>


> [!NOTE]  
> Il est important que vous terminiez la rubrique suivante, les <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">itinéraires de communications vocales modification à utiliser le nouveau serveur de médiation Lync Server 2013</A> pour vous assurer que les itinéraires de communications vocales pointent vers le serveur de médiation approprié.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

