---
title: Configuration du service de mobilité pour de hautes performances
TOCTitle: Configuration du service de mobilité pour de hautes performances
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690042(v=OCS.15)
ms:contentKeyID: 49298742
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du service de mobilité pour de hautes performances

 

_**Dernière rubrique modifiée :** 2013-02-17_

Lorsque vous installez le service de mobilité de Lync Server 2013 sur les services Internet (IIS) version 7.5, le programme d’installation du service de mobilité configure certains paramètres de performances sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Si vous utilisez les services Internet (IIS) 7.0 sur Windows Server 2008, vous devez configurer ces paramètres manuellement. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.

Les paramètres de performances sont les suivants :

  - **maxConcurrentThreadsPerCPU** a la valeur zéro (0).

  - **maxConcurrentRequestsPerCPU** a la valeur zéro (0).

  - Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).

  - La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).

Si vous utilisez les services Internet (IIS) 7.0, nous vous recommandons d’installer la mise à jour décrite dans l’article 2290617 de la Base de connaissances Microsoft, intitulé « CORRECTIF : Un correctif logiciel est disponible pour autoriser la configuration de certaines propriétés ASP.NET pour chaque pool d’applications dans les services Internet (IIS) 7.0 » et disponible à l’adresse [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x40c), de sorte que vous puissiez appliquer les modifications uniquement pour le service de mobilité, sans affecter d’autres services web.

La procédure suivante décrit comment modifier les valeurs maximales de threads et de demandes ASP.NET simultanées sur les services Internet (IIS) 7.0 si vous n’installez pas la mise à jour disponible dans l’article de la Base de connaissances 2290617. Toutefois, même si vous installez cette mise à jour, vous devez utiliser la documentation fournie par cet article pour appliquer les mêmes modifications uniquement pour les pools d’applications IIS de mobilité internes et externes. Dans ce cas, vous utilisez un fichier de configuration distinct pour les paramètres ASP.NET.

> [!IMPORTANT]  
> Si vous appliquez la procédure suivante pour modifier les valeurs maximales, les modifications affectent tous les pools d’applications IIS.

Pour plus d’informations sur la configuration de ces paramètres, voir [http://go.microsoft.com/fwlink/?linkid=234537\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=234537%26clcid=0x40c).

## Pour modifier les valeurs maximales de threads et de demandes simultanées

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la zone **Exécuter**, tapez ce qui suit :
    
        notepad %SystemRoot%\Microsoft.NET\Framework64\v2.0.50727\Aspnet.config

3.  Cliquez sur **OK**.

4.  Ajoutez ou remplacez l’élément \<system.web\> suivant comme enfant de l’élément \<configuration\> dans le fichier Aspnet.config :
    
        <system.web>
        <applicationPool maxConcurrentRequestsPerCPU="<#>" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>
        </system.web>
    
    où \# est égal à 0 pour supprimer la limite ou correspond au nouveau nombre comme décrit plus haut dans cette section.

5.  Enregistrez le fichier Aspnet.config et fermez le Bloc-notes.

