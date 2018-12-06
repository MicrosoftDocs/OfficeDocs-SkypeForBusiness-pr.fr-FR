---
title: 'Lync Server 2013 : Modification des certificats pour la mobilité'
TOCTitle: Modification des certificats pour la mobilité
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690015(v=OCS.15)
ms:contentKeyID: 49297168
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des certificats pour la mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-06-20_

Pour prendre en charge les connexions sécurisées entre votre environnement Lync et vos clients mobiles, les certificats SSL (Secure Socket Layer) de vos pool de directeurs, pool de serveurs frontaux et proxy inverses devront être mis à jour avec d’autres entrées SAN (Subject Alternative Name). Pour plus d’informations sur les exigences de certificat à des fins de mobilité, reportez-vous à la section « Exigences de certificat » dans [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mais vous devrez essentiellement obtenir d’autres certificats auprès de l’autorité de certification en intégrant ces nouvelles entrées SAN, puis ajouter ces certificats via la procédure décrite dans cet article.

Naturellement, avant de commencer, il est en général judicieux de connaître les autres noms d’objet figurant déjà sur vos certificats. Si vous ignorez les éléments déjà configurés, vous pouvez le savoir de différentes manières. Ces données seront tronquées alors que cette option permet d’exécuter **Get-CsCertificate** et d’autres commandes PowerShell pour afficher ces informations (que nous allons étudier ci-après) par défaut. Vous risquez donc de ne pas pouvoir visualiser toutes les propriétés nécessaires.Pour bien consulter le certificat et toutes ses propriétés, vous pouvez accéder à la console MMC (Microsoft Management Console) et charger le composant logiciel enfichable Certificats in (que nous étudierons également ci-après). Une autre soluton consiste à consulter l’Assistant Déploiement de Lync Server.

Comme indiqué plus phaut, la procédure suivante vous guidera tout au long de la mise à jour des certificats via le Lync Server Management Shell et la MMC. Si vous souhaitez utiliser l’Assistant Certificat dans l’Assistant Déploiement de Lync Server, vous pouvez vous reporter à [Configuration des certificats pour le directeur dans Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) pour le directeur ou pool directeur, si vous en avez configuré un (ce qui n’est peut-être pas le cas). Concernant le serveur ou le pool frontal, vous souhaiterez consulter [Configuration des certificats pour les serveurs dans Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Dernière chose à ne pas oublier : vous pouvez disposer d’un certificat par défaut unique dans votre environnement Lync Server 2013 ou de plusieurs certificats correspondant à Par défaut (tous les éléments à l’exception des services web), WebServicesExternal et WebServicesInternal. Cette procédure devrait vous être utile, quelle que soit votre configuration.

## Pour mettre à jour les certificats avec de nouveaux autres noms de l’objet via Lync Server Management Shell

1.  Vous devez vous connecter à votre serveur Lync Server 2013 via un compte disposant de droits et d’autorisations administrateur locaux. En outre, si vous exécutez la commande PowerShell **Request-CsCertificate** à partir de l’étape 12, ce compte devra disposer de plusieurs droits sur l’autorité de certification (AC) indiquée .

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Avant d’affecter un certificat mis à jour, vous devez connaître les certificats attribués au serveur et le type d’usage correspondant. Saisissez la syntaxe suivante dans la ligne de commande :
    
        Get-CsCertificate

4.  Consultez les résultats de l’étape précédente pour vérifier si un certificat unique a été attribué pour plusieurs utilisations, ou qu’un autre certificat est associé à chaque utilisation. Reportez-vous à la zone Utiliser le paramètre pour savoir comment un certificat est utilisé. Comparez le paramètre Thumbprint des certificats affichés pour déterminer si le même certificat est à usage multiples. Observez ce paramètre Thumbprint.

5.  Mettez à jour le certificat. Dans la ligne de commande, tapez ce qui suit :
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat avec Utilisation de la valeur par défaut, un autre avec Utilisation de WebServicesInternal et un autre avec Utilisation de WebServicesExternal, et qu’ils possédait tous la même valeur Thumbprint, vous devez saisir la syntaxe suivante dans la ligne de commande :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Important :**
    
    Si un autre certificat est associé à chaque utilisation (la valeur Thumbprint que vous avez cochée précédemment est différente pour chaque certificat), il est primordial que vous n’exécutiez **pas** l’applet de commande **Set-CsCertificate** avec plusieurs utilisations, comme dans l’exemple précédent. En l’occurrence, exécutez séparément l’applet de commande **Set-CsCertificate** pour chaque utilisation. Exemple :
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Pour afficher le ou les certificats, cliquez sur **Démarrer**, puis sur **Exécuter…**. Tapez MMC pour ouvrir la console MMC (Microsoft Management Console).

7.  Dans le menu de console MMC (Microsoft Management Console), sélectionnez **Fichier** , **Ajouter/Supprimer un composant logiciel enfichable** , puis Certificats. Cliquez sur **Ajouter** . Quand vous y êtes invité, sélectionnez **Compte d’ordinateur** , puis cliquez sur **Suivant** .

8.  S’il s’agit du serveur où le certificat est stocké, sélectionnez **Ordinateur local**. S’il est présent sur un autre ordinateur, vous devez choisir **Autre ordinateur**. Vous pouvez entrer le nom de domaine complet de l’ordinateur ou cliquer sur **Parcourir** dans **Entrez le nom de l’objet à sélectionner**, puis le nom de l’ordinateur. Cliquez sur **Vérifier les noms**. Ce nom est souligné lorsqu’il est résolu. Cliquez sur **OK**, puis sur **Terminer**. Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**.

9.  Pour afficher les propriétés du certificat, développez **Certificats** , développez **Personnel** , puis sélectionnez **Certificats** . Sélectionnez le certificat à afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **Ouvrir** .

10. Dans l’affichage **Certificat** , sélectionnez **Détails** . Vous pouvez ensuite sélectionner le nom d’objet du certificat en sélectionnant **Sujet** afin d’afficher le nom affecté et les propriétés associées.

11. Pour afficher les autres noms de l’objet affectés, sélectionnez **Autre nom de l’objet** . Tous les autres noms d’objet s’affichent dans cette zone. Les noms détectés sont par défaut de type **Nom DNS**. Vous devriez voir les membres suivants (ils doivent tous correspondre à des noms de domaine complets, tels qu’ils sont représentés dans les enregistrements d’hôte DNS (A ou AAAA, si IPv6 est en vigueur) :
    
      - Nom du pool ou du serveur unique (s’il ne s’agit pas d’un pool).
    
      - Nom du serveur auquel le certificat est affecté.
    
      - Enregistrements d’URL simples, généralement meet et dialin.
    
      - Noms internes et noms externes des services web (par exemple, webpool01.contoso.net, webpool01.contoso.com) en fonction des choix effectués dans le Générateur de topologie et des sélections de services web ayant été substituées.
    
      - S’ils sont déjà affectés, enregistrements lyncdiscover.\<domaine\_sip\> et lyncdiscoverinternal.\<domaine\_sip\>.
    
    Dernier élément vous intéressant le plus (si une entrée SAN lyncdiscover et lyncdiscoverinternal existe).
    
    Répétez ces étapes si vous devez vérifier plusieurs certificats. Une fois ces informations obtenues, vous pouvez fermer l’affichage du certificat et MMC.

12. S’il manque un autre nom de l’objet pour le service de découverte automatique et si vous utilisez un certificat par défaut unique pour les types Default, WebServicesInternal et WebServiceExternal, procédez comme suit :
    
      - Dans l’invite de commandes de Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous disposez de plusieurs domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Vous devez plutôt vous servir du paramètre DomainName. Dans ce cas, vous devez définir le FQDN pour les enregistrements lyncdiscoverinternal et lyncdiscover. Exemple :
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour affecter le certificat, tapez ce qui suit :
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour le certificat qui vient d’être émis.

13. Si un SAN interne de découverte automatique manque lors de l’utilisation de plusieurs paramètres pour Valeur par défaut, WebServicesInternal et WebServicesExternal, effectuez les opérations suivantes :
    
      - Dans l’invite de commandes de Lync Server Management Shell, tapez :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous disposez de plusieurs domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Vous devez plutôt employer le paramètre DomainName. Vous devez ajouter un préfixe approprié au FQDN du domaine SIP lorsque vous vous en servez. Exemple :
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Pour un autre nom de sujet du service de découverte automatique externe manquant, tapez ce qui suit dans la ligne de commande :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si vous disposez de plusieurs domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Vous devez plutôt employer le paramètre DomainName. Vous devez ajouter un préfixe approprié au FQDN du domaine SIP lorsque vous vous en servez. Exemple :
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Pour affecter les types de certificat individuel, tapez ce qui suit :
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour les certificats individuels qui viennent d’être émis.
    
    > [!NOTE]  
    > Remarque : les étapes 12 et 13 ne doivent être effectuées que si le compte les exécutant peut accéder à l’autorité de certification via les autorisations appropriées. Si vous ne pouvez pas vous connecter avec un compte doté de ces autorisations ou que vous utilisez une autorité de certification publique ou à distance pour vos certificats, vous devrez vous les demander par l’intermédiaire de l’Assistant Déploiement Lync Server, décrit au début de l’article.
