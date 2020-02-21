---
title: 'Lync Server 2013 : configuration de la déviation du trafic multimédia pour toujours contourner le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ae9bfa8be276cccc6f31def6fb7014e417841d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configuration de la déviation du trafic multimédia dans Lync Server 2013 pour toujours contourner le serveur de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

<div>


> [!NOTE]  
> Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des connexions de jonction vers un homologue (une passerelle PSTN, un PBX IP ou un contrôleur SBC chez un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le contournement de média contourne toujours le serveur de médiation.<BR>Vous ne pouvez pas configurer le contournement de média pour qu’il contourne toujours le serveur de médiation alors que le contrôle d’admission des appels est activé. Ces paramètres sont incompatibles et sont par conséquent mutuellement exclusifs dans l’interface utilisateur du panneau de configuration Lync Server.



</div>

Outre l’activation du contournement de média pour des connexions de jonction individuelles associées à un homologue vers le serveur de médiation, vous devez également configurer les paramètres globaux du contournement de média. Si vous utilisez les étapes de cette rubrique pour configurer les paramètres globaux pour la déviation du trafic multimédia, il est supposé que vous disposez d’une connexion correcte entre les points de terminaison Lync et tout homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.

Si vous n’avez pas une connectivité correcte entre les points de terminaison Lync Server et tous les homologues du serveur de médiation dont les connexions de jonction respectives ont été activées pour la déviation du trafic multimédia, vous devez configurer les paramètres globaux de contournement de média pour utiliser les informations de site et de région lorsque utilisation de la déviation du trafic multimédia. Cela permet de déterminer plus précisément le moment auquel le média contourne le serveur de médiation. Pour ce faire, suivez les étapes décrites dans [configure Media Bypass Global Settings in Lync Server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) , et [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Pour activer le contournement de média au niveau global pour qu’il contourne toujours le serveur de médiation

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Double-cliquez sur la configuration **Globale** dans la liste.

4.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.

5.  Cliquez sur **Toujours ignorer**.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Options globales de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Contournement de média et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

