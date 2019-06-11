---
title: 'Lync Server 2013: modifier l’URL des services Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Changer l’URL de services Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-11-16_

Lorsque vous configurez vos pools frontaux et les serveurs Standard Edition, vous avez la possibilité de configurer un nom de domaine complet (FQDN) externe et des ports associés. Si vous n’avez pas configuré cette URL lors de l’exécution de l’Assistant Déploiement de Lync Server, vous devez configurer vos paramètres manuellement. En règle générale, un administrateur n’a pas besoin de modifier ces paramètres, car il s’agit des ports recommandés et par défaut.

<div>


> [!NOTE]  
> La capture d’écran suivante a été prise lors de la configuration d’un serveur Standard Edition Server, de sorte que l’option de remplacement de nom de domaine complet est désactivée. Cette option est activée lors de la configuration d’un serveur Enterprise Edition dans un pool frontal.



</div>

![Modifier les paramètres du pool de services Web] (images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modifier les paramètres du pool de services Web")

<div>

## <a name="to-configure-web-services"></a>Pour configurer les services Web

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

3.  Dans le générateur de topologie, dans l’arborescence de la console sous **serveurs front end Standard Edition**, regroupements **front**end et pools d' **annuaires**, sélectionnez le nom du pool. Cliquez avec le bouton droit sur le nom, cliquez sur **modifier les propriétés**, puis cliquez sur **services Web**.

4.  Ajoutez ou modifiez le **nom de domaine complet des services Web externes**, puis cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal.

    
    </div>

5.  Vérifiez que les ports d’écoute et de publication sont configurés correctement pour votre environnement.

6.  Répétez ces étapes pour tous les serveurs Standard Edition, les listes frontales et les pools de directeurs de votre environnement.

7.  Dans l’arborescence de la console, cliquez sur **Lync Server 2013**, puis, dans le volet **actions** , cliquez sur nouvelle **topologie de publication**.

Quelques exigences sont à prendre en compte lorsque vous configurez les ports d’écoute et de publication:

  - Le port Listening indiqué est celui qui est configuré pour Internet Information Server (IIS) sur chaque serveur frontal.

  - Les ports d’écoute interne et externe doivent être différents pour les services Internet (IIS). Pour les ports d’écoute externes, ces derniers sont généralement les mêmes, car l’un représente l’équilibreur de charge matérielle pour le trafic Web interne et l’autre représente le serveur proxy inverse pour le trafic Web externe.

  - Vous pouvez remplacer les services Web internes sur un pool frontal, un réalisateur ou un pool de réalisateurs et définir votre propre nom de domaine complet.
    
    <div>
    

    > [!WARNING]  
    > Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs.

    
    </div>

  - Vous devez configurer les ports publiés sur le proxy inverse ou le service d’équilibrage de la charge matérielle comme ports d’écoute.

  - Dans le cas d’une réserve frontale (non illustrée dans l’exemple), le nom de domaine complet (FQDN) du pool SIP interne doit être différent du nom de domaine complet des services Web internes, car le trafic Web est transmis par le biais de l’équilibrage de charge DNS. . Cette obligation doit être remplie.

  - Le déploiement de Lync Server Standard Edition n’a pas besoin ou ne permet pas le remplacement de nom de domaine complet des services Web internes, car ce serveur ne peut pas être équilibré.

  - Si vous disposez d’un outil d’équilibrage de la charge matérielle dans votre environnement que vous utilisez pour le trafic SIP et Web interne, le générateur de topologie ne peut pas faire la distinction.
    
    Les noms de domaine complets de service Web doivent être facilement différenciés les uns des autres. Cela permet de s’assurer que la redirection d’URL pointe vers le serveur approprié. Par exemple, si vous avez deux noms de domaine complets, vous pouvez envisager d’attribuer un nom à un meeting.contoso.com et à l’autre conferencing.contoso.com. Vous risquez de rencontrer des problèmes de redirection si vous avez des noms de domaine complets portant des noms similaires, par exemple meet1.contoso.com et meet2.contoso.com.

Les services Web externes fonctionnent conjointement avec un proxy inverse dans le réseau de périmètre. Il offre aux clients un accès externe à l’aide de ces services Web. Les noms de domaine complets configurés ici sont envoyés aux clients lorsqu’ils ouvrent une session et permettent de rétablir une connexion HTTPs au proxy inverse lors de la connexion à distance. Le serveur proxy inverse transfère le nom de domaine complet du service Web externe à un équilibreur de charge matériel interne, ou directement au pool. Le proxy inverse doit être en mesure de résoudre le nom de domaine complet des services Web externes en adresse IP du serveur Web interne. Le FDQN des services Web externes doit être résolu sur l’Internet public.

Si votre serveur interne est un serveur Standard Edition Server, le FQDN interne est le FQDN du serveur Standard Edition. Si votre serveur interne est une réserve frontale, le nom de domaine complet est une adresse IP virtuelle d’équilibrage de charge matérielle qui charge les serveurs de batterie de serveurs Web internes. Un équilibrage de charge matérielle est requis dans un pool frontal doté de plus d’un serveur Enterprise Edition. Un équilibrage de charge n’est pas requis pour un serveur Standard Edition Server ou un serveur frontal Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

