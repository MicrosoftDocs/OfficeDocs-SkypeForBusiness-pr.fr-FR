---
title: Configuration des certificats pour la découverte automatique
TOCTitle: Configuration des certificats pour la découverte automatique
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945617(v=OCS.15)
ms:contentKeyID: 53095364
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour la découverte automatique

 

_**Dernière rubrique modifiée :** 2012-12-12_

Les certificats pour votre pool de directeurs, votre pool de serveurs frontaux et le proxy inverse nécessitent des entrées supplémentaires d’autres noms de l’objet afin de prendre en charge les connexions sécurisées avec les clients Lync.

> [!NOTE]  
> Vous pouvez utiliser l’applet de commande <strong>Get-CsCertificate</strong> pour afficher des informations sur les certificats actuellement affectés. Toutefois, l’affichage par défaut tronque les propriétés du certificat et n’affiche pas toutes les valeurs de la propriété SubjectAlternativeNames. Vous pouvez utiliser les applets de commande <strong>Get-CsCertificate</strong>, <strong>Request-</strong>CsCertificate et <strong>Set-CsCertificate</strong> pour afficher certaines informations, ainsi que pour demander et affecter des certificats. Cependant, ce n’est pas la meilleure méthode à utiliser si vous n’êtes pas sûr des propriétés des autres noms de l’objet (SAN) pour le certificat actuel. Pour afficher le certificat et tous les membres de propriété, nous vous suggérons d’utiliser le composant logiciel enfichable Certificats de <em>Microsoft Management Console (MMC)</em> ou l’Assistant Déploiement de Lync Server. Dans l’Assistant Déploiement de Lync Server, vous pouvez utiliser l’Assistant Certificat pour afficher les propriétés du certificat. Les procédures d’affichage, de demande et d’affectation d’un certificat à l’aide de Lync Server Management Shell et de <em>Microsoft Management Console (MMC)</em> sont détaillées dans les procédures suivantes. Pour utiliser l’Assistant Déploiement de Lync Server, si vous avez déployé le directeur ou le pool de directeurs (facultatifs), consultez les détails présentés dans <a href="lync-server-2013-configure-certificates-for-the-director.md">Configuration des certificats pour le directeur dans Lync Server 2013</a>. Pour le serveur frontal ou le pool de serveurs frontaux, consultez les détails présentés dans <a href="lync-server-2013-configure-certificates-for-servers.md">Configuration des certificats pour les serveurs dans Lync Server 2013</a>.<br />
Les étapes initiales de cette procédure sont des étapes de préparation qui vous orientent vers le rôle des certificats actuels. Par défaut, les certificats n’ont pas d’entrée lyncdiscover.&lt;domaine_sip&gt; ou lyncdiscoverinternal.&lt;nom_domaine_interne&gt;, sauf si vous avez installé au préalable le service Mobility Service ou si vous avez préparé vos certificats à l’avance. Cette procédure utilise l’exemple de nom de domaine SIP « contoso.com » et l’exemple de nom de domaine interne « contoso.net ».<br />
La configuration d’un certificat par défaut pour Lync Server 2013 et Lync Server 2010 consiste à utiliser un certificat unique (nommé « Default ») avec les finalités Default (pour toutes les finalités sauf les services web), WebServicesExternal et WebServicesInternal. La configuration facultative consiste à utiliser des certificats distincts pour chaque finalité. Les certificats peuvent être gérés à l’aide des applets de commande Lync Server Management Shell et Windows PowerShell, ou via l’Assistant Certificat de l’Assistant Déploiement de Lync Server.

## Pour mettre à jour les certificats avec de nouveaux autres noms de l’objet via Lync Server Management Shell

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte disposant de droits et d’autorisations d’administrateur local.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Déterminez les certificats qui ont été assignés au serveur et pour quel type d’utilisation. Vous aurez besoin de ces informations lors de l’étape suivante afin d’assigner le certificat mis à jour. Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsCertificate

4.  Examinez la sortie de l’étape précédente pour déterminer si un même certificat est assigné à plusieurs utilisations ou si un certificat différent est assigné à chaque utilisation. Observez le paramètre Use pour savoir comment un certificat est utilisé. Comparez le paramètre Thumbprint des certificats affichés pour savoir si le même certificat a plusieurs utilisations.

5.  Mettez à jour le certificat. Sur la ligne de commande, tapez ce qui suit :
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat avec comme utilisation « Default », un autre avec comme utilisation « WebServicesInternal  et un autre avec comme utilisation « WebServicesExternal » et que tous avaient la même valeur Thumbprint, tapez ce qui suit sur la ligne de commande :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Important :**
    
    Si un certificat différent est assigné pour chaque utilisation (la valeur de Thumbprint est différent pour chaque certificat), il ne faut surtout pas exécuter l’applet de commande **Set-CsCertificate** avec plusieurs types. Exécutez plutôt l’applet de commande **Set-CsCertificate** séparément pour chaque utilisation. Par exemple :
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Pour afficher le certificat, cliquez sur **Démarrer**, puis sur **Exécuter**. Tapez MMC pour ouvrir Microsoft Management Console.

7.  Dans le menu de Microsoft Management Console, sélectionnez **Fichier**, **Ajouter/Supprimer un composant logiciel enfichable**, puis Certificats. Cliquez sur **Ajouter**. Quand vous y êtes invité, sélectionnez **Compte d’ordinateur**, puis cliquez sur **Suivant**.

8.  Si le certificat se trouve sur cet ordinateur, sélectionnez **Ordinateur local**. Si le certificat est situé sur un autre ordinateur, sélectionnez **Autre ordinateur**, tapez le nom de domaine complet de l’ordinateur ou cliquez sur **Parcourir**. Dans **Entrez le nom de l’objet à sélectionner**, tapez le nom de l’ordinateur. Cliquez sur **Vérifier les noms**. Quand le nom de l’ordinateur sera résolu, il sera souligné. Cliquez sur **OK**, puis sur **Terminer**. Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**.
    
    > [!IMPORTANT]  
    > Si le certificat n’apparaît pas dans la console, vérifiez que vous n’avez pas sélectionné Utilisateur ou Service. Vous devez sélectionner Ordinateur pour localiser le certificat adéquat.

9.  Pour afficher les propriétés du certificat, développez **Certificats**, développez **Personnel**, puis sélectionnez **Certificats**. Sélectionnez le certificat à afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **Ouvrir**.

10. Dans l’affichage **Certificat**, sélectionnez **Détails**. Vous pouvez ensuite sélectionner le nom d’objet du certificat en sélectionnant **Sujet** afin d’afficher le nom affecté et les propriétés associées.

11. Pour afficher les autres noms de l’objet affectés, sélectionnez **Autre nom de l’objet**. Tous les autres noms de l’objet affectés sont affichés. Les autres noms de l’objet présents dans la propriété sont de type **Nom DNS** par défaut. Vous devriez voir les membres suivants (tous devraient correspondre à des noms de domaine complets tels qu’ils sont représentés dans les enregistrements d’hôte DNS, à savoir A ou AAAA si IPv6 est en vigueur) :
    
      - Nom de pool de ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool.
    
      - Nom du serveur auquel le certificat est affecté.
    
      - Enregistrements d’URL simples, généralement meet et dialin.
    
      - Noms internes et noms externes des services web (par exemple webpool01.contoso.net, webpool01.contoso.com) en fonction des choix effectués dans le Générateur de topologie et des sélections de services web ayant été substituées.
    
      - S’ils sont déjà affectés, enregistrements lyncdiscover.\<domaine\_sip\> et lyncdiscoverinternal.\<domaine\_sip\>.
    
    Le dernier élément est celui qui vous intéresse le plus (s’il existe une entrée d’autre nom de l’objet lyncdiscover et lyncdiscoverinternal).
    
    Une fois que vous avez ces informations, vous pouvez fermer l’affichage du certificat et MMC.

12. S’il manque un autre nom de l’objet pour le service de découverte automatique, ce qui signifie que l’autre nom de sujet lyncdiscover.\>nom de domaine\> et lyncdiscoverinternal.\<nom de domaine\> (selon qu’il s’agit d’un certificat externe ou interne) est manquant, et si vous utilisez un certificat par défaut unique pour les types Default, WebServicesInternal et WebServiceExternal, procédez comme suit :
    
      - Sur la ligne de commande de Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. À la place, vous devez utiliser le paramètre DomainName. Quand vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet des enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour affecter le certificat, tapez ce qui suit :
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour le certificat qui vient d’être émis.

13. S’il manque d’autres noms de l’objet pour la découverte automatique interne quand vous utilisez des certificats distincts pour les types Default, WebServicesInternal et WebServicesExternal, procédez comme suit :
    
      - Sur la ligne de commande de Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez ce paramètre, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour un autre nom de sujet du service de découverte automatique externe manquant, tapez ce qui suit sur la ligne de commande :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez ce paramètre, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Pour affecter les types de certificat individuel, tapez ce qui suit :
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour les certificats individuels qui viennent d’être émis.

