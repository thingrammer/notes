#### spring security

```java
Object principal = SecurityContextHolder.getContext().getAuthentication().getPrincipal();
```
```java
public interface Authentication extends Principal, Serializable { // <1>
    Collection<? extends GrantedAuthority> getAuthorities(); // <2>

    Object getCredentials();// <2>

    Object getDetails();// <2>

    Object getPrincipal();// <2>

    boolean isAuthenticated();// <2>

    void setAuthenticated(boolean var1) throws IllegalArgumentException;
}
```
```java
@Override
protected void configure(HttpSecurity http) throws Exception {
	http
		.authorizeRequests()
			.antMatchers("/resources/**", "/signup", "/about").permitAll()
             .antMatchers("/admin/**").hasRole("ADMIN")
             .antMatchers("/db/**").access("hasRole('ADMIN') and hasRole('DBA')")
             .anyRequest().authenticated()
			.withObjectPostProcessor(new ObjectPostProcessor<FilterSecurityInterceptor>() {
				public <O extends FilterSecurityInterceptor> O postProcess(
						O fsi) {
					fsi.setPublishAuthorizationSuccess(true);
					return fsi;
				}
			});
}
```