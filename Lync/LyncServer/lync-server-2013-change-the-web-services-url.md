---
title: 'Lync Server 2013 : modifier l’URL des services Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94424edc38cf1cc0eacac2638a4ed30a18f06779
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Modifier l’URL des services Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-16_

Lorsque vous configurez vos pools frontaux et vos serveurs Standard Edition, vous avez la possibilité de configurer un nom de domaine complet (FQDN) de batterie de serveurs web externes et des ports associés. Si vous n’avez pas configuré cette URL lors de l’exécution de l’Assistant Déploiement de Lync Server, vous devez configurer manuellement ces paramètres. Un administrateur n’a généralement pas besoin de modifier ces paramètres, puisqu’il s’agit des valeurs recommandées et des ports par défaut.

<div>


> [!NOTE]  
> La capture d’écran suivante a été effectuée lors de la configuration d’un serveur Standard Edition, de sorte que l’option remplacer le nom de domaine complet est désactivée. Cette option est activée lors de la configuration d’un serveur Enterprise Edition dans un pool frontal.



</div>

![Modifier les paramètres du pool des services Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modifier les paramètres du pool des services Web")

<div>

## <a name="to-configure-web-services"></a>Pour configurer les services Web

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

3.  Dans le générateur de topologie, dans l’arborescence de la console, sous **serveurs frontaux Standard Edition**, **Pools frontaux Enterprise Edition**et **pools de répertoires**, sélectionnez le nom du pool. Cliquez avec le bouton droit sur le nom, cliquez sur **Modifier les propriétés**, puis cliquez sur **Services web**.

4.  Ajoutez ou modifiez le **Nom de domaine complet (FQDN) des services web externes**, puis cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.

    
    </div>

5.  Vérifiez que les ports d’écoute et les ports publiés sont correctement configurés pour votre environnement.

6.  Répétez ces étapes pour tous les serveurs Standard Edition, pools frontaux et pools directeurs dans votre environnement.

7.  Dans l’arborescence de la console, cliquez sur **Lync Server 2013** puis, dans le volet **Actions**, cliquez sur **Publier la topologie**.

Vous devez respecter quelques conditions préalables lorsque vous configurez les ports d’écoute et de publication :

  - Les ports d’écoute présentés sont les ports configurés pour Internet Information Server (IIS) sur chaque serveur frontal.

  - Les ports d’écoute internes et externes doivent être différents pour IIS. En ce qui concerne les ports d’écoute externes, ils sont généralement identiques, car l’un représente le programme d’équilibrage de la charge matérielle pour le trafic web interne et l’autre représente le serveur proxy inverse pour le trafic web externe.

  - Vous pouvez remplacer les services Web internes sur un pool frontal, un directeur ou un pool directeur et définir votre propre nom de domaine complet.
    
    <div>
    

    > [!WARNING]  
    > Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.

    
    </div>

  - Les ports publiés doivent être configurés sur le proxy inverse ou le programme d’équilibrage de la charge matérielle en tant que ports d’écoute.

  - Pour un pool frontal (non présenté dans l’exemple), le nom de domaine complet (FQDN) du pool SIP interne doit être différent du nom de domaine complet (FQDN) des services web internes, car le trafic web passe par le programme d’équilibrage de la charge matérielle et le trafic du pool SIP interne passe par le programme d’équilibrage de la charge DNS. Cette condition préalable doit être respectée.

  - Un déploiement Lync Server Standard Edition n’a pas besoin ou n’autorise pas le remplacement d’un nom de domaine complet (FQDN) des services Web internes car ce serveur ne peut pas être équilibré en charge.

  - Si vous disposez d’un programme d’équilibrage de la charge matérielle dans votre environnement que vous utilisez pour le trafic SIP et Web interne, le générateur de topologies ne peut pas faire la distinction.
    
    Les noms de domaine complets des services Web doivent être facilement différenciés les uns des autres ; Cela permet de s’assurer que la redirection d’URL pointe vers le serveur approprié. Par exemple, si vous avez deux noms de domaine complets, vous pouvez nommer un meeting.contoso.com et l’autre conferencing.contoso.com. Vous pouvez potentiellement rencontrer des problèmes de redirection si vous avez des noms de domaine complets avec des noms plus similaires, tels que meet1.contoso.com et meet2.contoso.com.

Les services web externes fonctionnent conjointement avec un proxy inverse dans le réseau de périmètre. Elle offre aux clients un accès externe à l’aide de ces services Web. Les noms de domaine complets configurés ici sont envoyés aux clients quand ils se connectent et sont utilisés pour établir une connexion HTTPS au proxy inverse en cas de connexion à distance. Le serveur proxy inverse transfère le nom de domaine complet des services web externes à un appareil d’équilibrage de charge interne ou directement au pool. Le serveur proxy doit pouvoir résoudre le nom de domaine complet des services web externes en adresse IP du serveur web interne. Le nom de domaine complet des services web externes doit pouvoir être résolu sur le réseau Internet public.

Si votre serveur interne est un serveur Standard Edition, le nom de domaine complet interne est le nom de domaine complet du serveur Standard Edition. Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) du programme d’équilibrage de la charge matérielle, qui équilibre la charge des serveurs de la batterie de serveurs web internes. Un programme d’équilibrage de la charge matérielle est nécessaire dans un pool frontal comportant plusieurs serveurs Enterprise Edition. Un programme d’équilibrage de la charge n’est pas nécessaire pour un serveur Standard Edition ou un seul serveur frontal Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

