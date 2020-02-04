---
title: 'Lync Server 2013 : Configuration requise pour le plug-in Lync VDI'
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
ms.openlocfilehash: 51fb0081188618b6a5ea2951968effb0d55c4af7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Configuration requise pour le plug-in Lync VDI dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-07_

Dans un environnement VDI (Virtual Desktop Infrastructure), les machines virtuelles et l’ordinateur local de l’utilisateur doivent respecter les exigences indiquées dans cette section.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’installation et le déploiement de l’environnement virtualisé, voir votre fournisseur de solution de virtualisation. Pour plus d’informations sur le déploiement d’un environnement virtualisé basé sur Hyper-V et sur les services Bureau à distance, consultez les articles suivants dans la bibliothèque Microsoft TechNet : 
> <UL>
> <LI>
> <P>Hyper-V à<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Services Bureau à distance dans Windows&nbsp;Server&nbsp;2008 R2 sur<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Vous trouverez ci-dessous une configuration requise pour les machines virtuelles exécutées sur l’ordinateur du centre de données :

  - Les machines virtuelles doivent être configurées avec Windows 10, Windows 8,1, Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers Service Packs.

Pour l’utilisateur et l’ordinateur local de l’utilisateur, vous devez disposer des éléments suivants :

  - L’utilisateur doit être hébergé sur Lync Server 2013.

  - L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1, Windows 8, Windows 8,1 incorporé ou Windows 8,1 (non incorporé).

  - Si vous utilisez les services Bureau à distance, le nombre de bits du plug-in Lync VDI (c’est-à-dire, si l’application est 32 ou 64 bits) doit correspondre à la valeur de bits du système d’exploitation de l’ordinateur local. Il n’est pas nécessaire de faire correspondre le nombre binaire du système d’exploitation de l’ordinateur local et du système d’exploitation sur la machine virtuelle. Si vous utilisez une autre solution ou plateforme de virtualisation, consultez la rubrique recommandations de la part de votre fournisseur de solutions de virtualisation concernant les exigences de nombre de bits.

  - L’ordinateur local doit exécuter la version la plus récente du client de bureau à distance. Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel du client Bureau à distance de votre fournisseur de solutions de virtualisation. Pour obtenir les dernières mises à jour de services Bureau à [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)distance, voir.

  - Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés afin que le son soit lu sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, reportez-vous à la section « pour configurer les paramètres de connexion Bureau à distance ».

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Pour configurer les paramètres de connexion Bureau à distance

Pour préparer la connexion Bureau à distance dans Windows pour le plug-in Lync VDI, procédez comme suit.

1.  Si l’ordinateur local exécute Windows 8, ignorez cette étape. Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du client de services Bureau à distance, disponible [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)à l’adresse.

2.  Démarrez le client des services Bureau à distance en cliquant sur **Démarrer**, puis sur **Connexion Bureau à distance **.

3.  Cliquez sur **Options**.

4.  Cliquez sur l’onglet **Ressources locales**. Sous **Sortie audio de l’ordinateur distant **, cliquez sur **Paramètres**, puis procédez comme suit :
    
      - Sous **Lecture audio à distance**, sélectionnez **Lire sur cet ordinateur **.
    
      - Sous **Enregistrement audio à distance**, sélectionnez **Ne pas enregistrer **.
    
      - Cliquez sur **OK**.

5.  Cliquez sur l’onglet **Expérience**. Sous **Performance **, désactivez la case à cocher **Mise en cache permanente des bitmaps **.

6.  Cliquez sur l’onglet **général** . Dans **ordinateur**, tapez le nom de l’ordinateur virtuel, puis cliquez sur **se connecter**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

