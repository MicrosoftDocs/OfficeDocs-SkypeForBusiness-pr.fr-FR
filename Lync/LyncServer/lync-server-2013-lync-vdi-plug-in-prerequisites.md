---
title: 'Configuration requise pour le plug-in Lync Server 2013 : Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a5cde1ba7acae400bce7dd7ddf03b96c0338f26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Conditions préalables du plug-in Lync VDI dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-07_

Dans un environnement VDI (Virtual Desktop Infrastructure), les machines virtuelles et l’ordinateur local de l’utilisateur doivent satisfaire les exigences décrites dans cette section.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’installation et le déploiement de l’environnement virtualisé, reportez-vous à votre fournisseur de solutions de virtualisation. Pour plus d’informations sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les services Bureau à distance, consultez les articles suivants dans la bibliothèque Microsoft TechNet : 
> <UL>
> <LI>
> <P>Hyper-V à<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Services Bureau à distance dans Windows&nbsp;Server&nbsp;2008 R2 à l’adresse<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Les conditions suivantes sont requises pour les machines virtuelles qui s’exécutent sur l’ordinateur du centre de données :

  - Les ordinateurs virtuels doivent être configurés avec Windows 10, Windows 8,1, Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers Service Packs.

Les conditions suivantes sont requises pour l’utilisateur et l’ordinateur local de l’utilisateur :

  - L’utilisateur doit être hébergé sur Lync Server 2013.

  - L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1, Windows 8, Windows 8,1 Embedded ou Windows 8,1 (non incorporé).

  - Si vous utilisez les services Bureau à distance, le nombre de bits de plug-in Lync VDI (c’est-à-dire, si l’application est 32 bits ou 64 bits) doit correspondre au nombre de bits du système d’exploitation de l’ordinateur local. Le nombre de bits du système d’exploitation sur l’ordinateur local et le système d’exploitation sur l’ordinateur virtuel n’ont pas besoin de correspondre. Si vous utilisez une autre solution ou plateforme de virtualisation, reportez-vous à la rubrique instructions de votre fournisseur de solutions de virtualisation sur les spécifications de nombre de bits.

  - L’ordinateur local doit exécuter la dernière version du client Bureau à distance. Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel client Bureau à distance de votre fournisseur de solutions de virtualisation. Pour obtenir les dernières mises à jour des services Bureau à [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)distance, reportez-vous à.

  - Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés de manière à ce que l’audio s’exécute sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, reportez-vous à la section suivante, « pour configurer les paramètres de la connexion Bureau à distance ».

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Pour configurer les paramètres de la connexion Bureau à distance

Pour préparer la connexion Bureau à distance dans Windows pour le plug-in Lync VDI, procédez comme suit.

1.  Si l’ordinateur local exécute Windows 8, ignorez cette étape. Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du client des services Bureau à distance, disponible [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)à l’adresse.

2.  Démarrez le client des services Bureau à distance en cliquant sur **Démarrer**, puis sur **Connexion Bureau à distance**.

3.  Cliquez sur **Options**.

4.  Cliquez sur l’onglet **ressources locales** . Sous **audio à distance**, cliquez sur **paramètres**, puis procédez comme suit :
    
      - Sous **lecture audio à distance**, sélectionnez **lire sur cet ordinateur**.
    
      - Sous **enregistrement audio à distance**, sélectionnez **ne pas enregistrer**.
    
      - Cliquez sur **OK**.

5.  Cliquez sur l’onglet **expérience** . Sous **performances**, désactivez la case à cocher **mise en cache des bitmaps permanentes** .

6.  Cliquez sur l’onglet **général** . Dans **ordinateur**, tapez le nom de l’ordinateur virtuel, puis cliquez sur **se connecter**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

