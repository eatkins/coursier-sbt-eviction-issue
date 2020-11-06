This sbt build will not load because coursier resolves the classpath for
the plugins and the swoval source format plugin depends on sbt 1.3.0
but the build.sbt depends on the `usePipelining` key which was added
in 1.4.0. The sbt 1.3.0 jars end up evicting the 1.4.2 jars and the
build.sbt fails to compile as a result. If the swoval source format
plugin is removed from project/plugins.sbt, then the build loads.
