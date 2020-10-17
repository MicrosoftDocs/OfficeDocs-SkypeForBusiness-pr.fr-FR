---
title: 'Lync Server 2013 : modification des certificats pour la mobilité'
description: 'Lync Server 2013 : modification des certificats pour la mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555850"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modification des certificats pour la mobilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-20_

Pour prendre en charge les connexions sécurisées entre votre environnement Lync et vos clients mobiles, les certificats SSL (Secure Socket Layer) de votre pool de directeurs, de votre pool frontal et de votre proxy inverse doivent être mis à jour avec certaines entrées de SAN (autre nom de sujet) supplémentaires. Pour plus d’informations sur les exigences de certificat pour la mobilité, voir la section relative aux exigences de certificat dans la rubrique [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mais vous devez essentiellement obtenir de nouveaux certificats auprès de l’autorité de certification avec les entrées San supplémentaires incluses, puis ajouter ces certificats en suivant les étapes de cet article.

Bien entendu avant de commencer, il est généralement judicieux de savoir quels sont les autres noms de sujet que vos certificats possèdent déjà. Si vous n’êtes pas sûr de ce qui a déjà été configuré, il existe de nombreuses façons de le découvrir. Alors que l’option permet d’exécuter les commandes **Get-CsCertificate** et d’autres commandes PowerShell pour afficher ces informations, (ce qui est décrit ci-dessous) par défaut, les données sont tronquées, de sorte que vous ne pouvez pas voir toutes les propriétés dont vous avez besoin. Pour obtenir un bon aperçu du certificat et de toutes ses propriétés, vous pouvez accéder à la console MMC (Microsoft Management Console) et charger le composant logiciel enfichable Certificats (que nous allons également suivre ci-dessous), ou vous pouvez simplement vérifier l’Assistant Déploiement de Lync Server.

Comme indiqué ci-dessus, les étapes suivantes vous guideront tout au long du processus de mise à jour des certificats à l’aide de Lync Server Management Shell et de la console MMC. Si vous souhaitez plutôt utiliser l’Assistant certificat dans l’Assistant Déploiement de Lync Server pour cela, vous pouvez vérifier la [Configuration des certificats pour le directeur dans Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) pour le directeur ou le pool Directeur, si vous en avez configuré un (vous n’avez peut-être pas utilisé). Pour le serveur frontal ou le pool frontal, consultez la rubrique [configure Certificates for Servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Pour en savoir plus, il est possible que vous disposiez d’un seul certificat par défaut dans votre environnement Lync Server 2013 ou que vous disposiez de certificats distincts pour la valeur par défaut (tout sauf les services Web), WebServicesExternal et WebServicesInternal. Quelle que soit votre configuration, ces étapes doivent vous aider.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Pour mettre à jour les certificats avec de nouveaux noms de sujet alternatifs à l’aide de Lync Server Management Shell

1.  Vous devez vous connecter à votre serveur Lync Server 2013 à l’aide d’un compte disposant de droits et d’autorisations d’administrateur local. En outre, si vous exécutez la requête PowerShell **-CsCertificate** aux étapes 12 et ultérieures, le compte doit disposer de droits sur l’autorité de certification (ca) spécifiée.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Avant de pouvoir attribuer un certificat mis à jour, vous devez déterminer les certificats qui ont été attribués au serveur et le type d’utilisation. Sur la ligne de commande, tapez :
    
        Get-CsCertificate

4.  Passez en revue la sortie de l’étape précédente pour voir si un seul certificat a été affecté à plusieurs utilisations ou si un certificat différent est affecté à chaque utilisation. Recherchez le mode d’utilisation d’un certificat dans le paramètre use. Comparez le paramètre Thumbprint des certificats affichés pour savoir si le même certificat a plusieurs utilisations. Gardez votre oeil sur le paramètre empreinte numérique.

5.  Mettez à jour le certificat. Sur la ligne de commande, tapez ce qui suit :
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Par exemple, si la cmdlet **Get-CsCertificate** affiche un certificat avec utilisation de la valeur par défaut, une autre avec une utilisation de WebServicesInternal et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte, sur la ligne de commande, vous devez taper :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Important :**
    
    Si un certificat distinct est affecté à chaque utilisation (la valeur d’empreinte numérique que vous avez vérifiée ci-dessus est donc différente pour chaque certificat), il est vital que vous n’exécutiez **pas** la cmdlet **Set-CsCertificate** avec plusieurs types, comme dans l’exemple ci-dessus. Exécutez plutôt l’applet de commande **Set-CsCertificate** séparément pour chaque utilisation. Par exemple :
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Pour afficher le ou les certificats, cliquez sur **Démarrer**, puis sur **exécuter..**.. Tapez MMC pour ouvrir Microsoft Management Console.

7.  Dans le menu de Microsoft Management Console, sélectionnez **Fichier**, **Ajouter/Supprimer un composant logiciel enfichable**, puis Certificats. Cliquez sur **Ajouter**. Quand vous y êtes invité, sélectionnez **Compte d’ordinateur**, puis cliquez sur **Suivant**.

8.  S’il s’agit du serveur où se trouve le certificat, sélectionnez **ordinateur local**. Si le certificat se trouve sur un autre ordinateur, vous devez sélectionner **un autre ordinateur**, puis taper le nom de domaine complet de l’ordinateur ou cliquer sur **Parcourir** dans **Entrez le nom de l’objet à sélectionner**, puis tapez le nom de l’ordinateur. Cliquez sur **Vérifier les noms**. Lorsque le nom de l’ordinateur est résolu, il est souligné. Cliquez sur **OK**, puis sur **Terminer**. Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** .

9.  Pour afficher les propriétés du certificat, développez **Certificats**, développez **Personnel**, puis sélectionnez **Certificats**. Sélectionnez le certificat à afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **Ouvrir**.

10. Dans l’affichage **Certificat**, sélectionnez **Détails**. Vous pouvez ensuite sélectionner le nom d’objet du certificat en sélectionnant **Sujet** afin d’afficher le nom affecté et les propriétés associées.

11. Pour afficher les autres noms de l’objet affectés, sélectionnez **Autre nom de l’objet**. Tous les autres noms de sujet affectés sont affichés ici. Les autres noms du sujet trouvés ici sont de type **nom DNS** par défaut. Vous devriez voir les membres suivants (tous devraient correspondre à des noms de domaine complets tels qu’ils sont représentés dans les enregistrements d’hôte DNS, à savoir A ou AAAA si IPv6 est en vigueur) :
    
      - Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool
    
      - Nom du serveur auquel le certificat est affecté.
    
      - Enregistrements d’URL simples, généralement meet et dialin.
    
      - Noms externes des services Web et des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web remplacés.
    
      - S’il est déjà attribué, le lyncdiscover.\<sipdomain\> et lyncdiscoverinternal.\<sipdomain\> présents.
    
    Le dernier élément est celui qui intéresse le plus, s’il existe une entrée SAN lyncdiscover et lyncdiscoverinternal.
    
    Répétez ces étapes si vous avez plusieurs certificats à vérifier. Une fois que vous avez ces informations, vous pouvez fermer l’affichage du certificat et MMC.

12. S’il manque un autre nom de l’objet pour le service de découverte automatique et si vous utilisez un certificat par défaut unique pour les types Default, WebServicesInternal et WebServiceExternal, procédez comme suit :
    
      - À l’invite de ligne de commande Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour affecter le certificat, tapez ce qui suit :
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour le certificat qui vient d’être émis.

13. Pour un SAN de découverte automatique interne manquant lors de l’utilisation de certificats distincts pour default, WebServicesInternal et WebServicesExternal, procédez comme suit :
    
      - À l’invite de ligne de commande Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez le paramètre DomainName, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour un autre nom de sujet du service de découverte automatique externe manquant, tapez ce qui suit sur la ligne de commande :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez le paramètre DomainName, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Pour affecter les types de certificat individuel, tapez ce qui suit :
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour les certificats individuels qui viennent d’être émis.
    
    <div>
    

    > [!NOTE]  
    > Pour noter, les étapes 12 et 13 doivent être exécutées uniquement si le compte qui les exécute a accès à l’autorité de certification avec les autorisations appropriées. Si vous ne parvenez pas à vous connecter avec un compte qui dispose de ces autorisations, ou si vous utilisez une autorité de certification publique ou distante pour vos certificats, vous devez les demander via l’Assistant Déploiement Lync Server, qui a été touché en haut de l’article.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

