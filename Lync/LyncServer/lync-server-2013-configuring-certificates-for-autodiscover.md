---
title: 'Lync Server 2013 : configuration de certificats pour la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configuration de certificats pour la découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-12_

Les certificats de votre pool de réalisateurs, de votre pool frontal et du proxy inverse requièrent des entrées de nom alternatif supplémentaires pour la prise en charge de connexions sécurisées avec les clients Lync.

<div>


> [!NOTE]  
> Vous pouvez utiliser l’applet de cmdlet <STRONG>Get-CsCertificate</STRONG> pour afficher des informations sur les certificats actuellement attribués. Toutefois, le mode par défaut tronque les propriétés du certificat et n’affiche pas toutes les valeurs de la propriété SubjectAlternativeNames. Vous pouvez utiliser les applets de requête <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate et <STRONG>Set-CsCertificate</STRONG> pour afficher des informations et pour demander et affecter des certificats. Néanmoins, il ne s’agit pas de la meilleure méthode à utiliser si vous n’êtes pas sûr des propriétés des autres noms d’objet (SAN) sur le certificat actuel. Pour afficher le certificat et tous les membres de propriété, il est préférable d’utiliser le composant logiciel enfichable Certificats dans la <EM>console MMC</EM> ou utiliser l’Assistant Déploiement de Lync Server. Dans l’Assistant Déploiement de Lync Server, vous pouvez utiliser l’Assistant Certificat pour afficher les propriétés du certificat. Les procédures d’affichage, de demande et d’attribution d’un certificat à l’aide de Lync Server Management Shell et de <EM>Microsoft Management Console (MMC)</EM> sont décrites dans les procédures suivantes. Pour utiliser l’Assistant Déploiement de Lync Server, voir détails ici si vous avez déployé le directeur ou le pool de réalisateurs facultatif : <A href="lync-server-2013-configure-certificates-for-the-director.md">configurer des certificats pour le directeur dans Lync Server 2013</A>. Pour le serveur frontal ou le pool frontal, voir les détails ici : <A href="lync-server-2013-configure-certificates-for-servers.md">configurer des certificats pour les serveurs dans Lync Server 2013</A>.<BR>Les étapes initiales de cette procédure sont des étapes de préparation, qui vous permettent de vous orienter sur le rôle joué par les certificats actuels. Par défaut, les certificats n’ont pas de lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;nom&gt; de domaine interne, sauf si vous avez déjà installé les services de mobilité ou si vous avez préparé vos certificats à l’avance. Cette procédure utilise l’exemple de nom de domaine SIP’contoso.com’et l’exemple de nom de domaine interne’contoso.net'.<BR>La configuration de certificat par défaut pour Lync Server 2013 et Lync Server 2010 consiste à utiliser un certificat unique (nommé « par défaut ») avec les objectifs par défaut (pour tous les usages sauf pour les services Web), WebServicesExternal et WebServicesInternal. Une configuration facultative consiste à utiliser des certificats séparés pour chaque objectif. Les certificats peuvent être gérés en utilisant les applets de certification Lync Server Management Shell et Windows PowerShell, ou en utilisant l’Assistant certificat dans l’Assistant Déploiement de Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Pour mettre à jour les certificats avec d’autres noms d’objet à l’aide de Lync Server Management Shell

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte disposant de droits d’administrateur local et d’autorisations.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Déterminez les certificats attribués au serveur et le type d’utilisation. Vous avez besoin de ces informations lors de l’étape suivante pour affecter le certificat mis à jour. À partir de la ligne de commande, tapez :
    
        Get-CsCertificate

4.  Regardez dans la sortie de l’étape précédente pour voir si un certificat unique est affecté à plusieurs usages ou si un certificat différent est attribué à chaque utilisation. Dans le paramètre use, recherchez le mode d’utilisation d’un certificat. Comparez le paramètre d’empreinte numérique pour les certificats affichés pour déterminer si le même certificat a des usages multiples.

5.  Mettez à jour le certificat. À partir de la ligne de commande, tapez :
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat utilisant la valeur par défaut, une autre avec une utilisation de WebServicesInternal, et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte numérique, sur la ligne de commande, tapez :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Important :**
    
    Si un certificat distinct est attribué à chaque utilisation (la valeur de l’empreinte numérique est différente pour chaque certificat), il est important de ne pas exécuter l’applet de certification **Set-CsCertificate** avec plusieurs types. Dans ce cas, exécutez l’applet de la cmdlet **Set-CsCertificate** séparément pour chaque utilisation. Par exemple :
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Pour afficher le certificat, cliquez sur **Démarrer**, puis sur **exécuter...**. Tapez MMC pour ouvrir Microsoft Management Console.

7.  Dans le menu MMC, sélectionnez **fichier**, choisissez **Ajouter/supprimer un composant logiciel enfichable...**, puis sélectionnez certificats. Cliquez sur **Ajouter**. Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**, puis cliquez sur **suivant**.

8.  Si le certificat se trouve sur cet ordinateur, sélectionnez **ordinateur local**. Si le certificat se trouve sur un autre ordinateur, sélectionnez **un autre ordinateur**, tapez le nom de domaine complet de l’ordinateur ou cliquez sur **Parcourir** dans **entrer le nom de l’objet à sélectionner**, puis tapez le nom de l’ordinateur. Cliquez sur **vérifier les noms**. Lorsque le nom de l’ordinateur est résolu, il est souligné. Cliquez sur **OK**, puis sur **Terminer**. Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants additionnels** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si le certificat n’apparaît pas dans la console, assurez-vous que vous n’avez pas sélectionné d’utilisateur ou de service. Vous devez sélectionner ordinateur ou vous ne pouvez pas trouver le certificat probper.

    
    </div>

9.  Pour afficher les propriétés du certificat, développez **certificats**, **personnel**, puis sélectionnez **certificats**. Sélectionnez le certificat que vous voulez afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **ouvrir**.

10. Dans l’affichage **certificat** , sélectionnez **Détails**. À partir de cet emplacement, vous pouvez sélectionner le nom du sujet du certificat en sélectionnant **objet** et le nom de l’objet affecté ainsi que les propriétés associées apparaissent.

11. Pour afficher les noms de remplacement de l’objet affecté, sélectionnez **autre nom**de l’objet. Tous les noms de domaine alternatifs attribués sont affichés. Les noms d’objet alternatifs figurant dans la propriété sont de type **nom DNS** par défaut. Les membres suivants doivent s’afficher (qui doivent correspondre à des noms de domaine complets tels qu’ils sont représentées dans l’hôte DNS (A ou, si vous avez des enregistrements IPv6 AAAA) :
    
      - Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool
    
      - Nom du serveur auquel le certificat est affecté
    
      - Enregistrements d’URL simples, en règle générale et en ligne
    
      - Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.
    
      - S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.
    
    Le dernier élément correspond à ce qui est le plus intéressé, s’il y a une entrée lyncdiscover et lyncdiscoverinternal SAN.
    
    Une fois que vous disposez de ces informations, vous pouvez fermer l’affichage du certificat et la console MMC.

12. S’il s’agit d’un service de découverte automatique, c’est-à-dire le lyncdiscover. \>nom\> de domaine et lyncdiscoverinternal. \<nom\> de domaine (basé sur s’il s’agit d’un certificat externe ou interne) le nom de l’autre nom de l’objet est manquant et que vous utilisez un certificat par défaut unique pour les types WebServicesInternal et WebServiceExternal, procédez comme suit :
    
      - Dans l’invite de la ligne de commande Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre nom_domaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour attribuer le certificat, tapez ce qui suit :
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « empreinte » est l’empreinte digitale affichée pour le certificat nouvellement émis.

13. Pour les noms de remplacement de l’objet de découverte automatique manquantes lors de l’utilisation de certificats séparés par défaut, WebServicesInternal et WebServicesExternal, procédez comme suit :
    
      - Dans l’invite de la ligne de commande Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre nom_domaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le FQDN du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour un autre nom d’objet de découverte automatique externe manquant, sur la ligne de commande, tapez :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre nom_domaine. Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le FQDN du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Pour attribuer les types de certificats individuels, tapez les informations suivantes :
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « empreinte » est l’empreinte digitale affichée pour les certificats individuels émis.

</div>

</div>

<span> </span>

</div>

</div>

</div>

