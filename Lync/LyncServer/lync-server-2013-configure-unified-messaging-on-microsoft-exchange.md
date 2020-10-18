---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange'
description: 'Lync Server 2013 : configurez la messagerie unifiée sur Microsoft Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577520"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Cette rubrique décrit comment configurer la messagerie unifiée Exchange (MU) sur un serveur Microsoft Exchange Server pour une utilisation avec voix entreprise.

<div>


> [!NOTE]  
> Les exemples d’applets de commande fournis dans cette rubrique fournissent la syntaxe de la version Exchange 2007 de l’environnement de commande Exchange Management Shell. Si vous utilisez Exchange 2010 ou Exchange 2013, reportez-vous à la documentation appropriée, telle qu’elle est référencée.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Pour configurer un serveur exécutant la messagerie unifiée Exchange Server

1.  Créez un plan de numérotation URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) de messagerie unifiée pour chacun des profils d’emplacement Voix Entreprise. Si vous choisissez d’utiliser la console de gestion Exchange, créez un nouveau plan de numérotation avec le paramètre de sécurité **Secured (de préférence)**.
    
    <div>
    

    > [!WARNING]  
    > Si vous définissez votre valeur de paramètre de sécurité sur <STRONG>sécurisé SIP</STRONG> pour exiger le chiffrement pour le trafic SIP uniquement, comme précédemment recommandé, Notez que ce paramètre de sécurité sur un plan de numérotation est insuffisant si le pool frontal est configuré pour exiger le chiffrement, ce qui signifie que le pool nécessite le chiffrement pour le trafic SIP et RTP. Lorsque le plan de numérotation et les paramètres de sécurité du pool ne sont pas compatibles, tous les appels à la messagerie unifiée Exchange à partir du pool frontal échouent, ce qui entraîne une erreur indiquant que le paramètre de sécurité est incompatible.

    
    </div>
    
    Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, tapez :
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Pour plus d’informations, voir :
    
      - Pour Office Communications Server 2007, voir « procédure de création d’un plan de numérotation SIP de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) et « New-UMDialplan : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .
    
      - Pour Exchange 2010, voir « Création d’un plan de numérotation de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) et « New-UMDialplan : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .
    
      - Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
    <div>
    

    > [!NOTE]  
    > La sélection du niveau de sécurité <STRONG>SIPSecured</STRONG> ou <STRONG>Secured</STRONG> dépend de l’activation ou de la désactivation du protocole SRTP (Secure Real-time Transport Protocol) pour le chiffrement multimédia. Pour l’intégration de Lync Server 2010 avec la messagerie unifiée Exchange, cela doit correspondre au niveau de chiffrement dans la configuration multimédia de Lync Server. La configuration multimédia de Lync Server peut être affichée en exécutant la cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Pour plus d’informations, reportez-vous à Get-CsMediaConfiguration dans la documentation Lync Server Management Shell.<BR>Pour plus d’informations sur la sélection du paramètre de sécurité VoIP approprié, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et Lync Server 2013</A>.

    
    </div>

2.  Exécutez l’applet de commande suivante pour obtenir le nom de domaine complet (FQDN) pour chaque plan de numérotation de messagerie unifiée :
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Pour plus d’informations, voir :
    
      - Pour Exchange 2007, voir « Get-UMDialplan : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .
    
      - Pour Exchange 2010, voir « Get-UMDialplan : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .
    
      - Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .

3.  Enregistrez le nom de chaque plan de numérotation de messagerie unifiée. En fonction de votre version d’Exchange Server, vous devrez peut-être utiliser le nom de domaine complet (FQDN) de chaque nom de plan de numérotation par la suite, comme le nom du plan de numérotation Lync Server correspondant à chaque plan de numérotation de messagerie unifiée, afin que les noms de plan de numérotation
    
    <div>
    

    > [!NOTE]  
    > Les noms de plan de numérotation Lync Server doivent correspondre aux noms de plan de numérotation de messagerie unifiée uniquement si le plan de numérotation de messagerie unifiée est exécuté sur une version d’Exchange <EM>antérieure</EM> à Exchange 2010 SP1.

    
    </div>

4.  Ajoutez le plan de numérotation au serveur exécutant la messagerie unifiée Exchange comme suit :
    
      - Si vous choisissez d’utiliser la console de gestion Exchange, vous pouvez ajouter le plan de numérotation à partir de la feuille de propriétés du serveur. Pour des instructions spécifiques, voir la documentation du produit Exchange Server.
        
        Pour Exchange 2007, voir « procédure d’ajout d’un serveur de messagerie unifiée à un plan de numérotation » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .
        
        Pour Exchange 2010, voir « afficher ou configurer les propriétés d’un serveur de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .
        
        Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
      - Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, exécutez ce qui suit pour chaque serveur de messagerie unifiée Exchange :
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Avant d’effectuer l’étape suivante, vérifiez que tous les utilisateurs de Voix Entreprise ont été configurés avec une boîte aux lettres Exchange Server.<BR>Pour Exchange 2007, reportez-vous à la bibliothèque TechNet Exchange Server 2007 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .<BR>Pour Exchange 2010, reportez-vous à la bibliothèque TechNet Exchange Server 2010 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .<BR>Lorsque vous spécifiez une stratégie de boîte aux lettres pour chaque plan de numérotation créé à l’étape 1, vous pouvez sélectionner la stratégie par défaut ou une stratégie que vous avez créée.

    
    </div>

5.  Accédez à \<Exchange installation directory\> \\ scripts, puis, si Exchange est déployé dans une forêt unique, tapez :
    ```console
    exchucutil.ps1
    ```
    Ou, si Exchange est déployé dans plusieurs forêts, tapez ceci :
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    où Forest FQDN indique la forêt dans laquelle Lync Server est déployé.
    
    Si vous avez un ou plusieurs plans de numérotation de messagerie unifiée associés à plusieurs passerelles IP, passez à l’étape 6. Si chaque plan de numérotation est associé à une seule passerelle IP, ignorez l’étape 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Redémarrez le service <STRONG>frontal Lync Server</STRONG> (rtcsrv.exe) <EM>après</EM> avoir exécuté exchucutil.ps1. Dans le cas contraire, Lync Server ne détecte pas la messagerie unifiée dans la topologie.

    
    </div>

6.  À l’aide de l’environnement de ligne de commande Exchange Management Shell ou de la console de gestion Exchange, désactivez les appels sortants pour toutes les passerelles IP associées à chaque plan de numérotation, à l’exception d’une seule.
    
    <div>
    

    > [!NOTE]  
    > Cette étape est nécessaire pour garantir que les appels sortants par le serveur exécutant la messagerie unifiée Exchange Server vers des utilisateurs externes (comme dans le cas des scénarios de lecture sur téléphone) traversent le pare-feu d’entreprise de manière fiable.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lors de la sélection de la passerelle IP de messagerie unifiée, qui permet d’autoriser les appels sortants, choisissez celle qui est capable de gérer le plus grand volume de trafic. N’autorisez pas le trafic sortant via une passerelle IP qui se connecte à un pool de directeurs Lync Server. Évitez également les pools d’un autre site central ou site de succursale. Vous pouvez utiliser l’une des méthodes suivantes pour empêcher les appels sortants de transiter via une passerelle IP :

    
    </div>
    
      - Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, désactivez chaque passerelle IP en exécutant la commande suivante :
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Pour Exchange 2007, voir « Set-UMIPGateway : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .
        
        Pour Exchange 2010, voir « Set-UMIPGateway : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .
    
      - Si vous utilisez la console de gestion Exchange, désactivez la case à cocher **Autoriser les appels sortants via cette passerelle IP de messagerie unifiée**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre plan de numérotation URI SIP de messagerie unifiée est associé à une seule passerelle IP, n’interdisez pas les appels sortants via cette passerelle.

    
    </div>

7.  Créez un standard automatique de messagerie unifiée pour chaque plan de numérotation Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > N’incluez pas d’espaces dans le nom du standard automatique.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Pour plus d’informations, voir :
    
      - Pour Exchange 2007, voir « New-UMAutoAttendant : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .
    
      - Pour Exchange 2010, voir « New-UMAutoAttendant : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .
    
    L’étape suivante doit être effectuée pour chaque utilisateur une fois que vous avez activé les utilisateurs de Lync Server pour voix entreprise et que vous connaissiez leurs URI SIP.

8.  Associez les utilisateurs de la messagerie unifiée Exchange (chacun d’eux devant être configuré avec une boîte aux lettres Exchange) au plan de numérotation de messagerie unifiée et créez un URI SIP pour chaque utilisateur.
    
    <div>
    

    > [!NOTE]  
    > L' <STRONG>SIPResourceIdentifier</STRONG> dans l’exemple suivant doit être l’adresse SIP de l’utilisateur Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Pour obtenir des informations détaillées, voir :
    
      - Pour Exchange 2007, voir « Enable-UMMailbox : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .
    
      - Pour Exchange 2010, voir « Enable-UMMailbox : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

