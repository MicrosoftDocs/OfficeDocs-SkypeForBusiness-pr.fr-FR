---
title: 'Lync Server 2013 : Modification des certificats pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bccb901f241089a21fd7428e28b005f46e157300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modification des certificats pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-20_

Pour prendre en charge les connexions sécurisées entre votre environnement Lync et vos clients mobiles, les certificats SSL (Secure Socket Layer) pour votre pool de Directors, votre pool frontal et votre proxy inverse doivent être mis à jour avec un autre nom d’objet supplémentaire ( SAN). Pour plus d’informations sur les exigences en matière de certificat de mobilité, voir la section exigences relatives aux certificats dans les [exigences techniques de mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mais de la même façon que vous devez obtenir de nouveaux certificats à partir du Autorité de certification avec les entrées SAN supplémentaires incluses, puis ajoutez ces certificats en suivant la procédure décrite dans cet article.

Bien entendu, avant de commencer, il est généralement judicieux de savoir quel autre nom de l’objet possède déjà vos certificats. Si vous n’êtes pas sûr de ce que vous avez déjà configuré, il existe de nombreux moyens de le découvrir. Même si l’option est là pour exécuter la commande **Get-CsCertificate** et les autres commandes PowerShell pour afficher ces informations, (ce que nous allons voir ci-dessous) par défaut, les données sont tronquées de façon à ce que vous n’obteniez pas toutes les propriétés dont vous avez besoin. Pour obtenir une vue d’ensemble du certificat et de toutes ses propriétés, vous pouvez accéder à Microsoft Management Console (MMC) et charger le composant logiciel enfichable Certificats (que nous allons également suivre ci-dessous), ou vous pouvez simplement consulter l’Assistant Déploiement de Lync Server.

Comme indiqué plus haut, les étapes suivantes vous guident dans la mise à jour des certificats à l’aide de Lync Server Management Shell et de la console MMC. Si vous êtes intéressé par l’utilisation de l’Assistant certificat dans l’Assistant Déploiement de Lync Server pour ce faire, vous pouvez vérifier [configurer des certificats pour le directeur de Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) pour le directeur ou le pool de réalisateur, si vous en avez configuré un (vous ne pouvez pas avez). Pour le serveur frontal ou le pool frontal, vous pouvez voir [configurer des certificats pour les serveurs dans Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

En dernier lieu, il est possible que vous disposiez d’un seul certificat par défaut dans votre environnement Lync Server 2013 ou que vous ayez des certificats séparés par défaut (tout sauf les services Web), WebServicesExternal et WebServicesInternal. Quelle que soit la configuration, suivez les étapes ci-dessous pour vous aider.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Pour mettre à jour les certificats avec d’autres noms d’objet à l’aide de Lync Server Management Shell

1.  Vous devez vous connecter à votre serveur Lync Server 2013 à l’aide d’un compte disposant de droits d’administrateur local et d’autorisations. Par ailleurs, si vous exécutez la requête PowerShell **-CsCertificate** au cours des étapes 12 et ultérieures, le compte doit disposer de droits d’autorité de certification spécifiée.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour pouvoir attribuer un certificat mis à jour, vous devez identifier les certificats qui ont été attribués au serveur et le type d’utilisation. À partir de la ligne de commande, tapez :
    
        Get-CsCertificate

4.  Passez en revue la sortie de l’étape précédente pour voir si un seul certificat a été attribué pour plusieurs usages ou si un certificat différent est attribué à chaque utilisation. Dans le paramètre use, recherchez le mode d’utilisation d’un certificat. Comparez le paramètre d’empreinte numérique pour les certificats affichés pour déterminer si le même certificat a des usages multiples. Restez au coeur du paramètre d’empreinte numérique.

5.  Mettez à jour le certificat. À partir de la ligne de commande, tapez :
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat utilisant la valeur par défaut, une autre avec une utilisation de WebServicesInternal, et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte numérique, sur la ligne de commande, vous devez nouveau
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Important :**
    
    Si un certificat distinct est attribué à chaque utilisation (de sorte que la valeur de l’empreinte numérique que vous avez examinée ci-dessus est différente pour chaque certificat), il est essentiel que vous n’exécutiez **pas** l’applet de contrôle **Set-CsCertificate** avec plusieurs types, comme dans l’exemple ci-dessus. Dans ce cas, exécutez l’applet de la cmdlet **Set-CsCertificate** séparément pour chaque utilisation. Par exemple :
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Pour afficher le certificat (ou les certificats), cliquez sur **Démarrer**, puis sur **exécuter..**.. Tapez MMC pour ouvrir Microsoft Management Console.

7.  Dans le menu MMC, sélectionnez **fichier**, choisissez **Ajouter/supprimer un composant logiciel enfichable...**, puis sélectionnez certificats. Cliquez sur **Ajouter**. Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**, puis cliquez sur **suivant**.

8.  S’il s’agit du serveur sur lequel se trouve le certificat, sélectionnez **ordinateur local**. Si le certificat se trouve sur un autre ordinateur, vous devez sélectionner **un autre ordinateur**, puis taper le nom de domaine complet de l’ordinateur ou cliquer sur **Parcourir** dans **entrer le nom de l’objet pour le sélectionner**, puis taper le nom de ordinateur. Cliquez sur **vérifier les noms**. Lorsque le nom de l’ordinateur est résolu, il est souligné. Cliquez sur **OK**, puis sur **Terminer**. Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants additionnels** .

9.  Pour afficher les propriétés du certificat, développez **certificats**, **personnel**, puis sélectionnez **certificats**. Sélectionnez le certificat que vous voulez afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **ouvrir**.

10. Dans l’affichage **certificat** , sélectionnez **Détails**. À partir de cet emplacement, vous pouvez sélectionner le nom du sujet du certificat en sélectionnant **objet** et le nom de l’objet affecté ainsi que les propriétés associées apparaissent.

11. Pour afficher les noms de remplacement de l’objet affecté, sélectionnez **autre nom**de l’objet. Les noms de remplacement de l’objet affecté apparaissent ici. Le nom de remplacement de l’objet indiqué ici est de type **nom DNS** par défaut. Les membres suivants doivent s’afficher (qui doivent correspondre à des noms de domaine complets tels qu’ils sont représentées dans l’hôte DNS (A ou, si vous avez des enregistrements IPv6 AAAA):
    
      - Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool
    
      - Nom du serveur auquel le certificat est affecté
    
      - Enregistrements d’URL simples, en règle générale et en ligne
    
      - Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.
    
      - S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.
    
    Le dernier élément correspond à ce que vous êtes le plus intéressé par le biais d’une entrée SAN lyncdiscover et lyncdiscoverinternal.
    
    Répétez ces étapes si vous avez plusieurs certificats à vérifier. Une fois que vous disposez de ces informations, vous pouvez fermer l’affichage du certificat et la console MMC.

12. Si un autre nom de l’objet du service de découverte automatique est manquant et que vous utilisez un certificat par défaut unique pour les types WebServicesInternal et WebServiceExternal, procédez comme suit:
    
      - Dans l’invite de la ligne de commande Lync Server Management Shell, tapez:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre NomDomaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour attribuer le certificat, tapez ce qui suit:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où «empreinte» est l’empreinte digitale affichée pour le certificat nouvellement émis.

13. Pour un SAN de découverte automatique absent manquant lors de l’utilisation de certificats séparés par défaut, WebServicesInternal et WebServicesExternal, procédez comme suit:
    
      - Dans l’invite de la ligne de commande Lync Server Management Shell, tapez:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre NomDomaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le nom de domaine complet (FQDN) du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour un autre nom d’objet de découverte automatique externe manquant, sur la ligne de commande, tapez:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre NomDomaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le nom de domaine complet (FQDN) du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Pour attribuer les types de certificats individuels, tapez les informations suivantes:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où «empreinte» est l’empreinte digitale affichée pour les certificats individuels émis.
    
    <div>
    

    > [!NOTE]  
    > Remarque: les étapes 12 et 13 doivent être exécutées uniquement si le compte qui les exécute a accès à l’autorité de certification avec les autorisations appropriées. Si vous ne parvenez pas à vous connecter avec un compte qui dispose de ces autorisations, ou si vous utilisez une autorité de certification publique ou à distance pour vos certificats, vous devez les demander via l’Assistant Déploiement de Lync Server, qui a été touché en haut du bis.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

